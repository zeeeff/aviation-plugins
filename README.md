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
- Other ATAK plugins can query the data (identifier, nearest, search, area).

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
