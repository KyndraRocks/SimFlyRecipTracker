# SimFly Recip Tracker

A single-file reciprocation-tracking tool for SimFly airport owners. Tracks which pilots have flown to your airports, scores them by how overdue a return visit is, manages a welcome queue for new pilots, and hands off routes to Active Airports for flight planning.

**Current version: v2.62.0**

---

## Is this for you?

This is Kyndra's personal instance — it's hosted here so it runs from a real web address instead of a locally opened file (some features, like launching the Active Airports desktop app, need that). It isn't meant for other pilots to adopt as-is: your data lives in *your own* private GitHub Gist, so using this app means creating your own Gist and Personal Access Token.

**If you're another SimFly pilot looking for this kind of tracker,** use [Relationship Manager Lite](https://github.com/KyndraRocks/SimFly-Relationship-Manager) instead — it's the redistributable fork built for that, with no Gist or GitHub account required (everything stays local to your device, with optional file-based export/import).

---

## Download

Grab the latest release from the [Releases](https://github.com/KyndraRocks/SimFlyRecipTracker/releases) page, or open the hosted version directly: https://kyndrarocks.github.io/SimFlyRecipTracker/

---

## Data & Privacy

Your pilot/flight data is stored in a private GitHub Gist. On first load, the app asks for that Gist's ID and a GitHub Personal Access Token (`gist` scope) to connect. Neither is stored in this app's source code — both live only in your browser's local storage, entered once and (optionally) remembered on your device.

---

## Features

- **Balance Queue** — prioritizes which pilots to fly back to, scored by how overdue and how loyal each pilot is. Its filters — including the date-range slider that sets how far back the queue looks — are remembered between visits.
- **Quick Entry** — fast logging of inbound flights from your SimFly PAX wallet log.
- **Welcome Queue** — tracks new pilots who've flown in and haven't been welcomed yet.
- **Pilot Directory** — searchable roster of every tracked pilot and their airports.
- **Dashboard** — reciprocation history, filters, and CSV export.
- **Wallet** — SimFly PAX payout ledger tracking.
- **Pilot Payouts** — capture and sync payout rates without opening KML Generator.
- **Aircraft suitability** — pick an aircraft and set its fuel and payload, and every airport in the app is checked against it: an airport only counts as suitable if a single runway is long enough for the aircraft to both land there *and* take off again at that load, with the surface type, SimFly category, and the airport's density altitude all factored in. Hovering any airport code shows the takeoff and landing distances it needs, and says which of the two falls short when an airport doesn't qualify. The Balance Queue can be filtered down to just the pilots you can actually reach.
- **Plan Flight → Active Airports** — pick a departure/arrival pair and hand the route straight to Active Airports (web or desktop) for flight planning.

---

Public repo: https://github.com/KyndraRocks/SimFlyRecipTracker
