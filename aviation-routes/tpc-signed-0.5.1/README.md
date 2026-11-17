# Aviation Routes 0.5.1, TAK Product Center signed

`AviationRoutes-0.5.1-tpc-signed.apk` is Aviation Routes 0.5.1 built and signed
by the TAK Product Center third-party plugin pipeline (signer: "TAK Product
Center ATAK Untrusted Plugin Release").

- Runs on **release ATAK-CIV 5.8** (for example the Play Store build).
- It will **not** load in the developer ATAK from the SDK; for that, use the
  SDK-signed APK on the [Releases](https://github.com/zeeeff/aviation-plugins/releases) page.
- Source commit f902109, version code 16. Installs over the earlier signed
  builds (0.5.0 code 15, 0.4.5, 0.4.4).
- SHA-256: `8d647d145dc8e47a5542f78be624cbdd9058330fa47495e45551a81f21db2bd5`
- TPC's Fortify scan: no issues.

New since 0.5.0:
- Comms: a frequency can have a name of its own, shown small above it on the
  page and in the box on the map. A new kind of comm set, FREQ LIST: + FREQ
  adds numbered frequencies in order, and you can change a number. Presets
  can be sent (SEND on the PRESETS page) as a file to people, teams or a Data
  Sync mission; the receiver chooses ADD TO MINE or REPLACE MINE.
- Overlays panel: hold a button to open that section in the pane for
  editing.
- Mission rows: tap the binder icon to turn the mission on or off; Send on
  the row's second line.
- Route edit page: the distance heading reads LEG NM; tap it for CUM NM, the
  distance to go from your position along the route.
- Fix: Back could get stuck on a folder that no longer existed (after mission
  mode was turned off).

0.5.0 added: a TOOLS tab holding timeline, comms, rings and VI; comm cards per
mission (COMMEX, MISSION, A2A / A2G PACE and your own sets) with a frequency
pad (AM / FM / SAT, PT / TEK), presets and a box on the map, shared through
SEND, mission SHARE and Data Sync; an overlays button and panel on the map; a
keyhole overlay; the twilight popup for other nights; LZ role pairs; Send for
user waypoints; fixes for ATAK's large text mode.

0.4.5 added: the MISSION tab and mission mode, user waypoints, the Data Sync
icon on list rows, BE-NO lines and go-around arrows on LZ drawings, the HEMTT
fuel truck, the twilight bar and the timeline chip time picker. See the
[0.4.5 release](https://github.com/zeeeff/aviation-plugins/releases/tag/aviation-routes-v0.4.5)
for the full list.

Not for navigation or flight planning. Early build, not flight tested. See the
main README.
