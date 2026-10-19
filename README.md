# Aviation plugins for ATAK

Plugin downloads (APKs) for ATAK-CIV. Each plugin has its own releases,
tagged `<plugin>-v<version>`. Source code is kept elsewhere.

## Aero Data

Aeronautical data on the ATAK map: airports, airspace (class and special
use), navaids, waypoints, airways and military training routes.

- Sources: FAA NASR (US, 28-day cycle), OurAirports and openAIP (outside
  the US), and DAFIF from a file you provide. Each source can be downloaded
  in the plugin or loaded from a file.
- Tap an item for its info: key frequencies, runways, services, fuel,
  tower and ATIS, remarks. Search by identifier or name and drop a point.
- Other ATAK plugins can query the data (identifier, nearest, search, area):
  see [aero-data/API.md](aero-data/API.md).

### Install
1. Requires **ATAK-CIV 5.5.1, developer build** (from the ATAK 5.5.1 SDK).
   The APK is signed with the SDK development key, so release builds of
   ATAK will not load it.
2. Download the APK from
   [Releases](https://github.com/zeeeff/aviation-plugins/releases) and
   install it on the phone (or `adb install`).
3. In ATAK, open Plugins and load Aero Data, then open it from the Tools
   menu. Use MANAGE to download or load data.

Airspace outside the US needs your own free openAIP API key
(openaip.net, profile, API Clients).

### Data and use
- openAIP data is © openAIP, licensed CC BY-NC 4.0. OurAirports data is
  community maintained. FAA NASR is published by the FAA.
- No data ships with the plugin; each device downloads or loads its own.
- **Not for navigation.** Data may be incomplete or out of date; always
  check official publications.

## Range Rings

Fuel-based range rings for aircraft on the ATAK map: ferry range and combat
radius drawn as shaded circles around a point.

- Aircraft profiles: max gross weight, max fuel, fuel burn, loiter burn,
  reserve, start/taxi/takeoff fuel, ground speed (KGS). Fuel in pounds or
  liters. Ships with a UH-60 profile; add your own.
- Per flight: operating weight and fuel on board give ACL, ferry range,
  combat radius and endurance. Combat by **station time** (get the radius) or
  by **distance to target** (get the time on station).
- Center by map tap or marker, coordinates (MGRS), own position, or
  airport/navaid/fix search (needs **Aero Data**).
- Saved ring sets you can name, show/hide, go to, edit and redraw. Labels
  in whole NM. Rings are standard ATAK shapes, so they can be shared.
- Tap a ring for a Range Rings button on its menu.

### Install
1. Requires **ATAK-CIV 5.5.1, developer build** (from the ATAK 5.5.1 SDK).
   The APK is signed with the SDK development key, so release builds of
   ATAK will not load it.
2. Download the APK from
   [Releases](https://github.com/zeeeff/aviation-plugins/releases) and
   install it on the phone (or `adb install`).
3. In ATAK, open Plugins and load Range Rings, then open it from the Tools
   menu. Optional: install Aero Data for airport/navaid search.

### Use
- **Not for flight planning or navigation.** Figures are estimates from the
  numbers you enter; no wind is applied (speeds are ground speed). Always
  use approved performance data.

## Collective Routes

Route planning and navigation for helicopter crews on the ATAK map. Built
for night flying in an unstable aircraft: dark theme, big buttons, works
with gloves.

- Routes in folders. Add waypoints by map tap, coordinates (MGRS), an
  existing marker, own position, or airport/navaid/fix search (needs
  **Aero Data**). Auto-name mission points (STTO, SP, ACP, RP, TGT) with
  matching map symbols.
- Edit page: course, distance, ETE and ETA for each leg. Drag the route on
  the map, cross a waypoint on a heading, reverse or duplicate a route.
- Navigate: active leg in magenta, auto-sequencing, Direct-To, a Nav tab
  and a draggable map overlay.
- Time on target: one or more TOTs per route, with required ground speed,
  early/late, depart-at time, a TOT box on the map, passed times and
  touchdown time.
- Distance and time marks along the route, range rings around own
  position, and a track vector ahead of own position.
- Share routes with other ATAK users as `.croute` files.

### Install
1. Requires **ATAK-CIV 5.5.1, developer build** (from the ATAK 5.5.1 SDK).
   The APK is signed with the SDK development key, so release builds of
   ATAK will not load it.
2. Download the APK from
   [Releases](https://github.com/zeeeff/aviation-plugins/releases) and
   install it on the phone (or `adb install`).
3. In ATAK, open Plugins and load Collective Routes, then open it from the
   Tools menu. Optional: install Aero Data for waypoint search.

### Use
- **Not for navigation.** This is an early build and has not been flight
  tested: auto-sequencing, ETE/ETA and TOT numbers depend on GPS ground
  speed and have only been checked with simulated GPS. Use it as an aid
  alongside approved navigation sources.
