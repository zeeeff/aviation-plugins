# Aviation plugins for ATAK

Plugin downloads (APKs) for ATAK-CIV. Releases are tagged
`<plugin>-v<version>`. Source code is kept elsewhere.

## Collective

Route planning, fuel range rings and aeronautical data for helicopter crews,
in one plugin. Built for night flying in an unstable aircraft: dark theme,
big buttons, works with gloves. Four tabs:

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
- Navigate: active leg in magenta, auto-sequencing, Direct-To, a Nav tab and
  a draggable map overlay.
- Time on target: one or more TOTs per route, with required ground speed,
  early/late, depart-at time, a TOT box on the map, arrival and touchdown
  times.
- Distance and time marks along the route, range rings around own position,
  and a track vector ahead of own position.
- Share routes with other ATAK users as `.croute` files.

**Rings**
- Fuel-based ferry range and combat radius drawn around a point, from an
  aircraft profile (ships with a UH-60 profile; add your own), operating
  weight and fuel on board. Combat by station time or by distance to target.
- Saved ring sets in folders; show/hide, go to, edit and redraw.

**Aero**
- Airports, airspace (class and special use), navaids, waypoints, airways
  and military training routes on the map. Tap an item for frequencies,
  runways, services and remarks; search by identifier or name.
- Sources: FAA NASR (US, 28-day cycle), OurAirports and openAIP (outside the
  US), and DAFIF from a file you provide. No data ships with the plugin;
  each device downloads or loads its own.
- Other ATAK plugins can query the data: see
  [collective/API.md](collective/API.md).

**Settings**: time display, lat/long format, overlays, track vector, marks.

### Install
1. Requires **ATAK-CIV 5.8, developer build** (from the ATAK-CIV 5.8 SDK).
   The APK is signed with the SDK development key, so release builds of ATAK
   will not load it.
2. If you had the separate Range Rings or Aero Data plugins, uninstall them
   first. Collective replaces them and Collective Routes, and keeps their
   saved routes, ring sets and downloaded data.
3. Download the APK from
   [Releases](https://github.com/zeeeff/aviation-plugins/releases) and
   install it on the phone (or `adb install`).
4. In ATAK, open Plugins and load Collective, then open it from the Tools
   menu. Use the Aero tab to download or load aeronautical data.

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
