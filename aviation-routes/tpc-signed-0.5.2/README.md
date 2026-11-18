# Aviation Routes 0.5.2, TAK Product Center signed

`AviationRoutes-0.5.2-tpc-signed.apk` is Aviation Routes 0.5.2 built and signed
by the TAK Product Center third-party plugin pipeline (signer: "TAK Product
Center ATAK Untrusted Plugin Release").

- Runs on **release ATAK-CIV 5.8** (for example the Play Store build).
- It will **not** load in the developer ATAK from the SDK; for that, use the
  SDK-signed APK on the [Releases](https://github.com/zeeeff/aviation-plugins/releases) page.
- Source commit 30c6485, version code 17. Installs over the earlier signed
  builds (0.5.1 code 16, 0.5.0, 0.4.5, 0.4.4).
- SHA-256: `9c8cf7400a0d7390cb618c0b96f65b7527cf2474479976340316bfefd1573969`
- TPC's Fortify scan: no issues.

New since 0.5.1:
- LZ BLACK: a button at the top of the overlays panel. Tap the map (or long
  press to type a grid), then set the landing heading (°M), the formation
  (single, trail, echelon right, echelon left), how many aircraft and the
  aircraft type. The aircraft are placed on the heading, and go to Data Sync
  if the active mission is shared there.
- Point dropper: a small pin button beside LZ BLACK opens ATAK's Markers and
  Spot Map icons. Pick one and the palette shrinks to the name it will get
  (tap to rename); tap the map to place it, or long press to type
  coordinates. Shared to Data Sync with the active mission.
- Overlays panel: AIRSPACE now has AIRPORTS, E5, SUA and USER beside it, and
  three small colored lines showing the FAA, worldwide and DAFIF data dates
  (green current, red expired, gray not loaded).
- Route edit page: only the name opens a waypoint. Tap the NM column to
  switch leg / cumulative distance; the two ETE columns are now one that
  switches the same way.
- Auto naming: COUNT UP / COUNT DOWN beside AUTO NAME POINTS (remembered),
  and CONFIGURE WP NAMING to set your own names in place of STTO, SP, ACP,
  RP and TGT.

0.5.1 added: named frequencies, FREQ LIST comm sets, sending presets, hold to
edit in the overlays panel, mission row binder and Send, LEG NM / CUM NM. See
[tpc-signed-0.5.1](../tpc-signed-0.5.1) for the full list.

Not for navigation or flight planning. Early build, not flight tested. See the
main README.
