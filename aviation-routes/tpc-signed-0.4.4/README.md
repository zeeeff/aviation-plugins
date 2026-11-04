# Aviation Routes 0.4.4, TAK Product Center signed

`AviationRoutes-0.4.4-tpc-signed.apk` is Aviation Routes 0.4.4 built and signed
by the TAK Product Center third-party plugin pipeline (signer: "TAK Product
Center ATAK Untrusted Plugin Release").

- Runs on **release ATAK-CIV 5.8** (for example the Play Store build).
- It will **not** load in the developer ATAK from the SDK; for that, use the
  SDK-signed APK on the [Releases](https://github.com/zeeeff/aviation-plugins/releases) page.
- Source commit 2f4f8c5, version code 9. Installs over the signed 0.4.3 and
  over the first signed 0.4.4 (code 8), which it replaces.
- SHA-256: `07a4430dd69c176b2d120e4ef9b3617c5f354fffefb74c3d2fa5eb979507aed1`

New since 0.4.3: LZ roles (PRI / ALT INFIL, EXFIL, CASEVAC) on the LZ page and
radial, shown under the LZ name and on its marker; drawings and text labels
attached to an LZ (DRAW on the LZ page) that hide, move, send and sync with it;
route ETE / ETA and the time-mark calls in the Nav overlay box; a point within
10 m of an existing one asks before it is added; the coordinate pad keeps typed
digits across the 8 / 10 digit switch; hide from the radial menus; new items
follow their folder into a Data Sync mission; fixes for ghost waypoints, wrong
waypoint icons after a rename, crosshair time marks, and the pane opening over
ATAK's menus.

New in this build (code 9) over the first signed 0.4.4: routes, LZs and ring
sets keep the sender's folder when they are moved or their folder is renamed;
LZ drawings keep their LZ across restarts and follow its delete, move and
visibility from other devices; an LZ role is held by one LZ on every device;
two LZs no longer keep the same name; waypoint and VI names picked from an LZ
marker are one line; received text labels show as text only.

Not for navigation or flight planning. Early build, not flight tested. See the
main README.
