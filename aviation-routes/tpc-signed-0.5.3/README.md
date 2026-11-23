# Aviation Routes 0.5.3, TAK Product Center signed

`AviationRoutes-0.5.3-tpc-signed.apk` is Aviation Routes 0.5.3 built and signed
by the TAK Product Center third-party plugin pipeline (signer: "TAK Product
Center ATAK Untrusted Plugin Release").

- Runs on **release ATAK-CIV 5.8** (for example the Play Store build).
- It will **not** load in the developer ATAK from the SDK; for that, use the
  SDK-signed APK on the [Releases](https://github.com/zeeeff/aviation-plugins/releases) page.
- Source commit a0eec78, version code 18. Installs over the earlier signed
  builds (0.5.2 code 17, 0.5.1, 0.5.0, 0.4.5, 0.4.4).
- SHA-256: `cdc3cf5b81a46b4c44c9134a0cdca699b30776b0e7a93e684fb9a5e1a615442a`
- TPC's Fortify scan: no issues.

New since 0.5.2:
- COMMS: PRESETS is now SAVED FREQS. New PRESET PLANNER for the radio's
  preset files (.ini): list, import, send, copy, rename and write them to the
  SD card. Presets are added a step at a time, from saved freqs or from the
  comm card, with only the options the radio's own planner offers; a value
  stays red until it is in range.
- Frequency pads put the decimal point in as you type.
- Haptics: a light buzz on button taps, two on a refused entry, and a buzz
  for a route mark's call. On / off in SETTINGS, DISPLAY.
- Nav tab: leg keys beside the leg's name, the TOT block only when the route
  has a TOT. Tapping the nav box opens NAV. The route's name is in its tab
  row. Opening another route while moving on one asks first.
- TOT: tap the time to type it on a key pad, CLEAR TOT in the same dialog,
  the time shown in the waypoint's tag. Required ground speed over 150 kt
  reads ">150". ETE of an hour or more reads hours+minutes ("1+05").
- Adding waypoints by map tap keeps going until Back. New routes start at
  the planned speed last set.
- LZ: a new LZ opens its page; LANDING places aircraft on any LZ by heading,
  formation and type. EARLY is amber, like LATE.
- Point dropper names match ATAK's own.
- Fixes: lists that stopped responding after leaving a page and coming back;
  renaming a mission's folder in a tab split the mission; decimals rounded
  to one place on the number pad; a touch beside a pad discarded the entry;
  long editors pushing OK off a landscape phone; Android Back closing the
  whole pane.
- Consistency: a held DELETE needs no question and a tapped one asks; a name
  or number already used is refused inside its box; the map switches live in
  the overlays panel only; RINGS styled like the rest.

0.5.2 added: LZ BLACK, the point dropper, aero data dates in the overlays
panel, auto naming options. See [tpc-signed-0.5.2](../tpc-signed-0.5.2).

Not for navigation or flight planning. Early build, not flight tested. See the
main README.
