# Changelog

All releases of Cyclone Lite, the Android 6.0+ edition of [Cyclone](https://github.com/zakusworo/cyclone-beta).
Download them from [Releases](https://github.com/zakusworo/cyclone-lite/releases); the app also offers each new
version as a notification.

Version numbers follow the Cyclone version a release is built from (Lite 0.14.4 = Cyclone 0.14.4); the last
number goes up for Lite's own fixes.

## 0.14.6 · 2026-11-09

**Fixed**
- **Weather forecast not updating after rides without altitude.** Before a ride goes online, Cyclone Lite fills
  in missing heights from terrain data. Several such rides in one sync used up the weather service's per-minute
  limit within seconds, and everything after them failed, the forecast included. The forecast now updates
  first, and Cyclone Lite waits out the per-minute limit (about a minute) instead of giving up. Checked on
  Android 6.0.1 with five rides waiting.
- **Bluetooth sensors not found while Location is off.** Android 6 to 11 show no Bluetooth sensors to apps
  while the Location switch is off. The pairing window now says so and asks you to turn Location on, instead
  of searching in vain.

## 0.14.5 · 2026-11-08

**Fixed**
- **Stops along the route never appeared** on Android 6 to 9 (water, minimarkets, toilets, bike shops on the
  Ahead page). Their map server, overpass-api.de, now only accepts TLS 1.3 connections, which Android has from
  version 10. Cyclone Lite now asks public mirrors that still accept older phones, one after another until one
  answers (a busy one is asked once more first).
- **"Finish" at the start of out-and-back routes.** On a route that comes back along the same road, the
  position could be matched to the way home: the turn card said "Finish" and the distance to go read 0.2 km a
  few hundred metres into a 2 km route. You now stay on the way out until you have turned around, also when
  the ride was started away from the route.

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
- Stops along the route (water, minimarkets, toilets) don't load on Android 6 to 9 yet (fixed in 0.14.5).
- On Android 6 and 7 offline maps download over a plain connection; each map is checked against its known size
  and header before it is used.
