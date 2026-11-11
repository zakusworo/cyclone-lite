# Changelog

All releases of Cyclone Lite, the Android 6.0+ edition of [Cyclone](https://github.com/zakusworo/cyclone-beta).
Download them from [Releases](https://github.com/zakusworo/cyclone-lite/releases); the app also offers each new
version as a notification.

Version numbers follow the Cyclone version a release is built from (Lite 0.14.4 = Cyclone 0.14.4); the last
number goes up for Lite's own fixes.

## 0.15.3 · 2026-11-12 · Tamaki

Everything new in [Cyclone 0.15.3](https://github.com/zakusworo/cyclone-beta/releases/tag/v0.15.3), on Android 6 and newer.

**New**
- **Type the size on your tyre.** The tyre list in Gear (edit a bike → Tyre size) now starts with *Type the size
  on the tyre*: enter it as printed on the side, like `26 x 1.50`, `700x25C`, `650b x 47`, `26 x 1-3/8` or the two
  numbers `40-559`, and Cyclone Lite shows the wheel size as you type. Sizes in Garmin's wheel-size table use Garmin's
  measured value; others are worked out from the size. The wheel field on the Sensors screen takes a size too.
- **Your own brand and model.** Not in the list? The brand and model lists now start with *Not listed? Type your
  own brand…*, and what you type shows at the top as *Use "…"*.
- **More tyre sizes** from Garmin's table, including 26 × 1.50, 26 × 1.75, 26 × 1-3/8, 27 × 1-1/4 and the 650 sizes.

**Fixed**
- **Stops ahead on Android 8 and 9.** On these versions Cyclone Lite could reach only some of the backup stops servers;
  one of them was refused because of a missing security certificate. Cyclone Lite now includes it. (The servers
  themselves were overloaded on 11–12 November, so a download may still need another try.)
- **700 × 30C** was set to 2170 mm; Garmin's table says 2146 mm. Road, gravel, city and touring bikes on
  700 × 30C move to 2146 mm by themselves.
- An unreadable stops file no longer closes the ride screen.

## 0.15.2 · 2026-11-11 · Jervois

Everything fixed in [Cyclone 0.15.2](https://github.com/zakusworo/cyclone-beta/releases/tag/v0.15.2), on Android 6 and newer.

**Fixed**
- **Stops ahead missing on some routes.** When the OpenStreetMap server answered a route's stops search with
  an empty list (it sometimes does when it is busy, without saying so), Cyclone Lite kept that empty list for good and
  never searched again, so the Ahead page kept saying *Stops not downloaded yet* however often you synced. Now
  an empty answer is checked with a second server, kept for 6 hours at most, and **Sync now** always searches
  again. Routes that showed no stops get them at the next sync.
- **An empty GPX no longer replaces your route.** A downloaded GPX can hold only the route's name and
  no points (it happened with a RideWithGPS download). Importing one used to overwrite your route of the same
  name; now Cyclone Lite says the file has no points and keeps your route.

**Better**
- **Faster sync for a new route.** Stops now download before the BMKG weather warnings, and **Sync now** skips
  warnings fetched in the last 10 minutes. A busy stops server is left after 75 seconds instead of being waited
  on for minutes and then asked again, and the Online screen shows which server Cyclone Lite is waiting on.
- **Sync now** no longer starts a second sync while one is running; it tells you what the running one is doing.
- When a search really found no stops along a route, the Ahead and Online screens now say so, instead of
  *not downloaded yet*.

## 0.15.1 · 2026-11-10 · Britomart

Everything new in [Cyclone 0.15.1](https://github.com/zakusworo/cyclone-beta/releases/tag/v0.15.1), on Android 6 and newer.
Checked on a Galaxy J2 Prime (Android 6.0.1): first fix 94 s after GPS started indoors, walk outside included, ±11 m.

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
