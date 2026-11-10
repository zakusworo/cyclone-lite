# Changelog

All releases of Cyclone Lite, the Android 6.0+ edition of [Cyclone](https://github.com/zakusworo/cyclone-beta).
Download them from [Releases](https://github.com/zakusworo/cyclone-lite/releases); the app also offers each new
version as a notification.

Version numbers follow the Cyclone version a release is built from (Lite 0.14.4 = Cyclone 0.14.4); the last
number goes up for Lite's own fixes.

## 0.15.1 · 2026-11-10 · Britomart

Everything new in [Cyclone 0.15.1](https://github.com/zakusworo/cyclone-beta/releases/tag/v0.15.1), on Android 6 and newer.
Checked outdoors on a Galaxy J2 Prime (Android 6.0.1): first fix in 34 s after the first satellite was heard.

**New**
- **Faster GPS start.** When the phone's last GPS fix is more than an hour old, Cyclone Lite now asks Android for
  fresh GPS time and satellite orbit data as GPS starts (at most every 30 minutes, and again while it
  searches if the phone comes online later). With it, a first fix under open sky takes seconds instead of
  minutes on most phones. Phones with a MediaTek chip fetch their own orbit data and take only the time.
- **Why GPS is slow, on screen.** With no fix 90 seconds after GPS starts, the ride screen says either
  *No satellites yet · needs open sky* (the phone hears nothing: indoors, under a roof, or a covered pocket)
  or *GPS searching · N satellites heard* (it hears them and is still working out the position).
- **GPS log in problem reports.** Cyclone Lite keeps a short log of what GPS did: when it started, satellites heard
  while searching, how long the first fix took and how accurate it was. Problem reports (Options → Beta &
  updates → Send problem report) now include it, since some phones hide this from Android's own log.

## 0.15.0 · 2026-11-09 · O'Connell

Everything new in [Cyclone 0.15.0](https://github.com/zakusworo/cyclone-beta/releases/tag/v0.15.0), on Android 6 and newer.

**New**
- **Ride insights.** The summary of every ride now opens with an **Insights** card: a label for the kind of
  ride, a few sentences on how it went, and up to seven short notes, each with a line on what it means:
  personal bests, how the ride compares with your earlier rides of a similar distance, pacing and why one
  half was slower, wind and temperature at the time (Open-Meteo), effort and recovery with a heart-rate
  sensor or power meter, the biggest climb, stops, calories and goals. Everything is worked out on the
  phone; only an approximate location (about 1 km) and the date go to Open-Meteo for the weather.
  Checked on a Galaxy J2 Prime (Android 6.0.1, 540 × 960 screen).

**Fixed**
- **Thousands of metres of climbing on rides without altitude.** One GPS fix far away made the terrain
  lookup follow a straight line to it: a test ride showed 15,000 m on 1.8 km. It now follows the ride's own
  distance. Rides filled in by earlier versions are filled in again once, by themselves.
- **Climbing speed (VAM) in the summary's Climbs list** was too high on phones that write records less
  often than once a second; it now uses the real riding time.

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
