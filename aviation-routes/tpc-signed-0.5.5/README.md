# Aviation Routes 0.5.5, TAK Product Center signed

`AviationRoutes-0.5.5-tpc-signed.apk` is Aviation Routes 0.5.5 built and signed
by the TAK Product Center third-party plugin pipeline (signer: "TAK Product
Center ATAK Untrusted Plugin Release").

- Runs on **release ATAK-CIV 5.8** (for example the Play Store build).
- It will **not** load in the developer ATAK from the SDK; for that, use the
  SDK-signed APK on the [Releases](https://github.com/zeeeff/aviation-plugins/releases) page.
- Source commit cfea2fe, version code 20. Installs over the earlier signed
  builds (0.5.4 code 19, 0.5.3, 0.5.2, 0.5.1, 0.5.0, 0.4.5, 0.4.4).
- SHA-256: `b55f3fc5fcf334ec5b20e01f8f9be2bd4dea206bcb05b103a46fd978129c4283`
- TPC's Fortify scan: no issues.

New since 0.5.4:
- Data Sync: the hidden markers that carry a timeline and a comm card sit
  at their mission (its first route waypoint, LZ, waypoint or ring center;
  the map center for no mission) instead of 0°N 0°E, where ATAK's Overlay
  Manager listed them. Markers already at 0,0 move once, and that move goes
  through Data Sync too.
- Data Sync: the one-time re-send of mission items after the update runs
  once per device, as intended. In 0.5.4 it repeated as new items arrived,
  sending each one back to the mission.
- Comms: VHF airband frequencies (108 to 137 MHz) default to AM, as UHF
  from 225 MHz already did. Lines you saved keep their mode.
- TOTs on different days show the day, and a time typed on the key pad
  lands on the nearest day, not always today.
- The starting leg is right on very long legs too.
- Timeline list rows with a single timed event show that time.
- More large-text (accessibility) fixes.

0.5.4 added: timelines and comm cards in Data Sync missions, the TOT list,
mission TOTs on timelines, ROLL, swipe to delete, the starting leg, preset
files in comms. See [tpc-signed-0.5.4](../tpc-signed-0.5.4).

Not for navigation or flight planning. Early build, not flight tested. See the
main README.
