# Aviation Routes 0.4.4, TAK Product Center signed

`AviationRoutes-0.4.4-tpc-signed.apk` is Aviation Routes 0.4.4 built and signed
by the TAK Product Center third-party plugin pipeline (signer: "TAK Product
Center ATAK Untrusted Plugin Release").

- Runs on **release ATAK-CIV 5.8** (for example the Play Store build).
- It will **not** load in the developer ATAK from the SDK; for that, use the
  SDK-signed APK on the [Releases](https://github.com/zeeeff/aviation-plugins/releases) page.
- Source commit 4d85a83, version code 10. Installs over the signed 0.4.3 and
  over the earlier signed 0.4.4 builds (codes 8 and 9), which it replaces.
- SHA-256: `778ee9b883679e80eb61a4f3bcb343525226fcc0a6c2d1e2c483e26e2e45712f`

New since 0.4.3: LZ roles (PRI / ALT INFIL, EXFIL, CASEVAC) on the LZ page and
radial, shown under the LZ name and on its marker; drawings and text labels
attached to an LZ (DRAW on the LZ page) that hide, move, send and sync with it;
route ETE / ETA in the Nav overlay box; a point within 10 m of an existing one
asks before it is added; the coordinate pad keeps typed digits across the
8 / 10 digit switch; hide from the radial menus; new items follow their folder
into a Data Sync mission; fixes for ghost waypoints, wrong waypoint icons after
a rename, crosshair time marks, and the pane opening over ATAK's menus.

Code 9 added: routes, LZs and ring sets keep the sender's folder when they are
moved or their folder is renamed; LZ drawings keep their LZ across restarts and
follow its delete, move and visibility from other devices; two LZs no longer
keep the same name; waypoint and VI names picked from an LZ marker are one
line; received text labels show as text only.

New in this build (code 10): the time-mark calls (ADJ, CROSSED, T/D) show in
the TOT box, which keeps groundspeed after crossing; any number of LZs may
carry the same role, and roles travel with a shared LZ; reordering waypoints
or events shows the gap before you let go; the clock defaults to local time;
and an experimental **Timeline** tab (off by default in Settings): quick
timelines with 15 preset events, your own saved events, a Sun Data button
that adds Sunset and EENT for your position, a clock keypad or typed text per
event, a map overlay, and sharing with the custom events included.

Not for navigation or flight planning. Early build, not flight tested. See the
main README.
