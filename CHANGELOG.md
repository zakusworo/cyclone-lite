# Changelog

All releases of Cyclone Lite, the Android 6.0+ edition of [Cyclone](https://github.com/zakusworo/cyclone-beta).
Download them from [Releases](https://github.com/zakusworo/cyclone-lite/releases); the app also offers each new
version as a notification.

Version numbers follow the Cyclone version a release is built from (Lite 0.14.4 = Cyclone 0.14.4); the last
number goes up for Lite's own fixes.

## 0.14.4 · 2026-11-08

The first Cyclone Lite: everything in Cyclone 0.14.4, made to run on Android 6.0 and 7.

**New**
- **Runs on Android 6.0 and newer** (Cyclone needs 8.0). Tested on a Samsung Galaxy J2 Prime (Android 6.0.1,
  1.5 GB): GPS and satellites, recording and saving rides, offline maps, turn-by-turn with street names and
  spoken calls, and the map page.
- **Online services on old Android.** Android before 7.1.1 doesn't trust Let's Encrypt, which most of
  Cyclone's services use (weather, bike routing, map search, crash alerts, update checks); Cyclone Lite brings
  the certificates itself.
- **Fits small screens.** On narrow phones (like 5" 540×960 screens) the whole app is drawn a little smaller,
  so the home and ride screens fit without cut-off buttons.
- **CYCLONE LITE** on the home screen, and an Organic Maps shortcut in place of Komoot and Strava, which need
  Android 8.

**Known limits**
- Stops along the route (water, minimarkets, toilets) don't load on Android 6 to 9 yet.
- On Android 6 and 7 offline maps download over a plain connection; each map is checked against its known size
  and header before it is used.
