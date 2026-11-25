# Aviation Routes 0.5.4, TAK Product Center signed

`AviationRoutes-0.5.4-tpc-signed.apk` is Aviation Routes 0.5.4 built and signed
by the TAK Product Center third-party plugin pipeline (signer: "TAK Product
Center ATAK Untrusted Plugin Release").

- Runs on **release ATAK-CIV 5.8** (for example the Play Store build).
- It will **not** load in the developer ATAK from the SDK; for that, use the
  SDK-signed APK on the [Releases](https://github.com/zeeeff/aviation-plugins/releases) page.
- Source commit 21da4c1, version code 19. Installs over the earlier signed
  builds (0.5.3 code 18, 0.5.2, 0.5.1, 0.5.0, 0.4.5, 0.4.4).
- SHA-256: `5a1a0fcd5e95d150712f891a909884e40ca08a7698b9b5c1894cb3dd7d0758f8`
- TPC's Fortify scan: no issues.

New since 0.5.3:
- Data Sync: timelines and comm cards now go into Data Sync missions and
  their edits follow (Data Sync had been leaving them out). Each item says
  when its folder is a mission, so the mission shows on the receiving device
  whatever the Data Sync mission is called. After the update, items already
  in a mission are sent once more so devices that join later see it too.
  Both devices need 0.5.4.
- TOTs: a route with several opens a list of them all, with -10 -5 -1 /
  +1 +5 +10 on each and ADJUST ALL on top, taken together at OK (one TOT
  can pass another on the way). A new TOT is first offered at the planned
  ground speed along the route.
- Timeline: a mission route's TOTs appear as events and follow the route.
  ROLL moves every event still ahead by minutes. Swipe a row to delete it.
- A route made active starts on the leg you are at: the first leg at the
  STTO, or the leg you are on or flying toward.
- Comms: the pad's SAVED list includes your radio preset files, and SAVED
  FREQS and frequency lists have FROM PRESET FILE. A frequency from a file
  keeps the whole preset (and PSK / FSK / CPM), so it goes back into a file
  unchanged. Swipe to delete on the comms rows.
- Large text (accessibility): rows grow and values shrink to fit instead of
  being cut off; dialogs scroll. Hold EDIT renumbers waypoints again.

Known in this build (fixed for the next one): TOTs on different days show
only the clock time, so they can look out of order; a time typed on the
key pad lands on today's date; on very long legs (thousands of miles) the
starting leg can be the wrong one.

0.5.3 added: SAVED FREQS and the PRESET PLANNER, haptics, the nav tab and
TOT dialog changes. See [tpc-signed-0.5.3](../tpc-signed-0.5.3).

Not for navigation or flight planning. Early build, not flight tested. See the
main README.
