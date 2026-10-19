# Aero Data: API for other plugins

Aero Data answers location lookups for other ATAK plugins running in the
same ATAK process. There are two ways in:

1. **Broadcast query** (recommended): send an intent, get a reply intent.
2. **Read the database directly**: open the SQLite file read-only.

Only the winning copy of each item is returned. When the same item comes
from several sources, the priority is DAFIF, then FAA NASR, then
OurAirports, then openAIP.

## 1. Broadcast query

Send with `AtakBroadcast.getInstance().sendBroadcast(intent)` and listen
for the reply action you name.

Request: action `com.atakmap.android.aerodata.QUERY`

| Extra | Type | Notes |
|---|---|---|
| `op` | String | `ident`, `nearest`, `search` or `area` |
| `replyAction` | String | Required. The reply is broadcast with this action. Make it unique to your plugin. |
| `requestId` | String | Optional. Echoed back so you can match replies. |
| `kinds` | String[] | Optional. Any of `airport`, `navaid`, `waypoint`, `airspace`. Default: the three point kinds. |

Per operation:

| `op` | Extras | Returns |
|---|---|---|
| `ident` | `ident` (String) | Exact match on identifier. Airports also match ICAO and local id (e.g. `ATL` finds KATL). |
| `nearest` | `lat`, `lon` (double), `count` (int, default 10), `maxNm` (double, default 100) | Closest first, with `distanceNm` and `bearingTrue` added. |
| `search` | `text` (String), `limit` (int, default 50) | Identifier match, or name contains the text. Waypoints match by identifier prefix. |
| `area` | `north`, `south`, `east`, `west` (double), `limit` (int, default 500) | Everything inside the box. Airspace: boxes that overlap it. |

Reply: action = your `replyAction`

| Extra | Type |
|---|---|
| `requestId` | String (as sent) |
| `count` | int |
| `results` | `ArrayList<Bundle>` (`getParcelableArrayListExtra("results")`) |
| `error` | String, only if the query failed |

Each result Bundle has `kind`, `source` (`FAA_NASR`, `OURAIRPORTS`,
`OPENAIP`, `DAFIF`), `ident`, `id` (row id, stable until the source is
reloaded), plus:

- **airport**: `icao`, `localId`, `name`, `type` (LARGE, MEDIUM, SMALL,
  HELIPORT, SEAPLANE), `lat`, `lon`, `elevFt` (NaN if unknown), `country`,
  `towered`, `military`, `longestRunwayFt`, `runways`, `frequencies`.
  - `runways` is records separated by `;`, each
    `ident|lengthFt|widthFt|surface|hard(0/1)|lat1|lon1|lat2|lon2`.
  - `frequencies` is records separated by `;`, each `type|description|MHz`.
  - `details` is a JSON array of `[section, label, value]`, in display
    order; empty if the source has none.
    - FAA: Services (fuel, repair, oxygen, fees, customs, beacon, pattern
      altitude…), Attendance, Weather station, Tower, ATIS, Contacts, Remarks.
    - OurAirports: User comments (unofficial; label is the date).
    - openAIP, added to the matching OurAirports airport with " (openAIP)"
      after the section name: Services, Hours, Phone, Contacts, Remarks.
- **navaid**: `name`, `type` (VOR, VOR_DME, VORTAC, TACAN, DME, NDB,
  NDB_DME), `frequency` (MHz for VHF aids, kHz for NDBs), `channel`, `lat`,
  `lon`, `elevFt`, `country`.
- **waypoint**: `type` (as published by the source), `lat`, `lon`,
  `country`, `region`.
- **airspace**: `id`, `name`, `type` (CLASS_A–G, CLASS_E_SURFACE, CLASS_E5,
  RESTRICTED, PROHIBITED, WARNING, DANGER, MOA, ALERT, TRAINING, NSA, …),
  `lower`, `upper` (text such as `SFC`, `2500 MSL`, `FL180`), `country`, and
  the bounding box `north`, `south`, `east`, `west`. The outline isn't
  included; read the database if you need it.

### Example

```java
final String REPLY = "com.example.myplugin.AERO_REPLY";

BroadcastReceiver rx = new BroadcastReceiver() {
    @Override
    public void onReceive(Context c, Intent i) {
        ArrayList<Bundle> results = i.getParcelableArrayListExtra("results");
        if (results == null || results.isEmpty())
            return;
        Bundle first = results.get(0);
        double lat = first.getDouble("lat"), lon = first.getDouble("lon");
        // ...
    }
};
AtakBroadcast.DocumentedIntentFilter f = new AtakBroadcast.DocumentedIntentFilter();
f.addAction(REPLY, "Aero Data replies");
AtakBroadcast.getInstance().registerReceiver(rx, f);

Intent q = new Intent("com.atakmap.android.aerodata.QUERY");
q.putExtra("op", "ident");
q.putExtra("ident", "KATL");
q.putExtra("replyAction", REPLY);
AtakBroadcast.getInstance().sendBroadcast(q);
```

If Aero Data isn't installed or loaded, no reply arrives. Use a timeout.

## 2. Read the database directly

File: `FileSystemUtils.getItem("tools/aerodata/aerodata.sqlite")`, which is
usually `/sdcard/atak/tools/aerodata/aerodata.sqlite`. Open it with
`SQLiteDatabase.OPEN_READONLY`. It uses WAL mode, so reading works while
Aero Data is writing.

Tables: `airport`, `navaid`, `waypoint`, `airspace`, `route`. Always add
`WHERE hidden=0` to get one copy per item. Enum columns (`type`, `kind`)
store the ordinal of the matching enum in
`com.atakmap.android.aerodata.model`, and `source` stores the ordinal of
`data.Source` (0 FAA_NASR, 1 OURAIRPORTS, 2 OPENAIP, 3 DAFIF). The schema
may change between versions (`PRAGMA user_version` gives it), so the
broadcast query is the stable interface.
