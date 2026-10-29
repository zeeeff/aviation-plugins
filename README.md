# Aviation plugins for ATAK

Plugin downloads (APKs) for ATAK-CIV. Releases are tagged
`<plugin>-v<version>`. Source code is kept elsewhere.

## Aviation Routes

Route planning, fuel range rings, landing zones, vehicle interdiction and
aeronautical data in one plugin, built for helicopter crews but usable by
anyone planning a route on the map. Dark theme, big buttons, works with
gloves. Six tabs:

**Routes**
- Routes in folders. Tap a route's name to navigate it (magenta = active),
  tap it again to stop. Swipe a row right to delete.
- Add waypoints by map tap, an existing marker, own position, airport /
  navaid / fix search, or coordinates on a built-in MGRS or lat/long keypad
  (no system keyboard). Auto-name mission points (STTO, SP, ACP, RP, TGT)
  with matching map symbols.
- Edit page: course, distance, ETE and ETA for each leg. Hold and drag
  waypoints and legs on the map, cross a waypoint on a heading, reverse or
  duplicate a route.
- Navigate: active leg in magenta, auto-sequencing, Direct-To (from the map
  or from the nav box: search a point or enter coordinates), a Nav tab and a
  draggable map overlay. A MED Direct To spot (plugin-wide or per route) is
  one tap away on the nav box menu.
- Time on target: one or more TOTs per route, with required ground speed,
  early/late, depart-at time, a TOT box on the map, arrival and touchdown
  times.
- Distance and time marks along the route (timing marks can announce with a
  countdown box), an RP inbound time between the last two legs, range rings
  around own position, and a track vector ahead of own position.

**Rings**
- Fuel-based ferry range and combat radius drawn around a point, from an
  aircraft profile (ships with a UH-60 profile; add your own), operating
  weight and fuel on board. Combat by station time or by distance to target.
- Saved ring sets in folders; show/hide, go to, edit and redraw.

**LZ**
- Landing zones in folders (a folder is a mission). Drop an LZ on the map
  and pick where it sits in the mission area (N / E / S / W / C); it gets
  the next unused name from that letter's list, or type your own.
- Place ATAK's 3D aircraft models at the LZ (helicopters by default); rename
  them and set their heading. Hide or show an LZ with its aircraft at once.
- Direct To, zoom to, and send from the LZ page.

**VI**
- Vehicle interdiction: pick a route or drawn line, a moving unit on it and
  a point on the line. The plugin shows the unit's distance and time to
  that point along the line, its ETA, your own straight-line time and the
  age of its last report, in a draggable box on the map.

**Aero**
- Airports, airspace (class and special use), navaids, waypoints, airways
  and military training routes on the map. Tap an item for frequencies,
  runways, services and remarks; search by identifier or name.
- Sources: FAA NASR (US, 28-day cycle), OurAirports and openAIP (outside the
  US), and DAFIF from a file you provide. Each device downloads or loads its
  own, or receives it from another user (below).
- Other ATAK plugins can query the data: see
  [aviation-routes/API.md](aviation-routes/API.md).

**Settings**: time display, lat/long format, MED Direct To, overlays, track
vector, default route markers and RP inbound time, LZ name lists and which
aircraft the LZ dropper offers, VI box.

**Sending to other users**
- Long-press a route, ring set, LZ or folder (or use Send on a map menu, on
  a ring set or LZ page, or under an aero source) to open ATAK's contact
  list: people, teams or a Data Sync mission.
- Routes, ring sets, LZs and VI tracks travel as ATAK map items, not files.
  Everyone sees an ordinary ATAK route, the circles, or the LZ point and
  aircraft; Aviation Routes users get the full object (plan, TOTs, marks,
  the ring set's inputs, the LZ) in their list. Folders keep their names.
- Through a Data Sync mission they stay live: an edit on one device follows
  on the others, and removing an item from the mission removes it
  everywhere. Your active leg, Direct To and passed times stay on your
  device.
- Aero sources are files, loaded and drawn by the receiver (Data Sync needs
  its Auto download setting on, or open the mission and tap the file).
- DAFIF is distribution-limited: send it only to recipients authorized to
  receive it.

### Install
1. Requires **ATAK-CIV 5.8**. Two builds:
   - The APK on the Releases page is signed with the SDK development key and
     loads only in the **developer build** of ATAK (from the ATAK-CIV 5.8 SDK).
   - [aviation-routes/tpc-signed-0.4](aviation-routes/tpc-signed-0.4) has
     version 0.4 signed by the TAK Product Center, for **release ATAK**
     (for example the Play Store build). 0.4.1 has been submitted; its
     signed build will be added here when it comes back.
2. If you had the separate Range Rings or Aero Data plugins, uninstall them
   first. Aviation Routes replaces them and Collective Routes, and keeps
   their saved routes, ring sets and downloaded data.
3. Download the APK from
   [Releases](https://github.com/zeeeff/aviation-plugins/releases) and
   install it on the phone (or `adb install`).
4. In ATAK, open Plugins and load Aviation Routes, then open it from the
   Tools menu (rotor icon). Use the Aero tab to download or load
   aeronautical data. A short user manual is built in.

Airspace outside the US needs your own free openAIP API key (openaip.net,
profile, API Clients).

### Use
- **Not for navigation or flight planning.** This is an early build and has
  not been flight tested: auto-sequencing, ETE/ETA and TOT numbers depend on
  GPS ground speed and have only been checked with simulated GPS. Range
  rings are estimates from the numbers you enter with no wind applied.
  Aeronautical data may be incomplete or out of date. Always use approved
  navigation sources, performance data and official publications.
- openAIP data is © openAIP, licensed CC BY-NC 4.0. OurAirports data is
  community maintained. FAA NASR is published by the FAA.
