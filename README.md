# SimFly Recip Tracker

A single-file reciprocation-tracking tool for SimFly airport owners. Tracks which pilots have flown to your airports, scores them by how overdue a return visit is, manages a welcome queue for new pilots, and hands off routes to Active Airports for flight planning.

**Current version: v2.64.0**

---

## Is this for you?

This is Kyndra's personal instance — it's hosted here so it runs from a real web address instead of a locally opened file, which browsers treat differently in ways some features depend on. It isn't meant for other pilots to adopt as-is: your data lives in *your own* private GitHub Gist, so using this app means creating your own Gist and Personal Access Token.

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
- **Pilot activity** — the queue also knows how much each pilot actually flies, drawn from SimFly's public Sky Ranking. An **Activity** column shows their flight count over a window you choose (7, 30 or 90 days), and a **Flights** column gives their all-time career total. Read together they separate a pilot worth cultivating from one who used to be busy and has since gone quiet — flying a return leg to someone who has stopped playing earns nothing back. Two filters follow from it: show only pilots active at least N times in the window, or with at least N flights all-time. The 90-day figure is assembled here from daily snapshots rather than fetched, since SimFly only publishes 24-hour, 7-day, 30-day and all-time boards, so it deepens over time and says how much history stands behind it.
- **Opportunity score** (optional) — one 0–100 column answering “who is worth flying to next”. It combines how loudly a relationship asks for attention (visits owed, and how overdue you are) with how likely a return flight is to bring future traffic back (their activity), and it multiplies the two rather than adding them — so a dormant pilot scores near zero however many visits they owe. Hovering a score shows exactly how it was reached, and three sliders let you steer the balance. Off by default; the other columns stay raw counts.
- **Flight history** — expanding a pilot's row draws their whole back-and-forth with you as a chart: inbound visits and your outbound flights on one timeline, thirty days in view at a time and scrollable back through the full history. Hovering anywhere on it snaps a crosshair to the nearest day and reports that date with both counts.
- **Quick Entry** — fast logging of inbound flights from your SimFly PAX wallet log.
- **Welcome Queue** — tracks new pilots who've flown in and haven't been welcomed yet.
- **Pilot Directory** — searchable roster of every tracked pilot and their airports.
- **Dashboard** — reciprocation history, filters, and CSV export.
- **Wallet** — SimFly PAX payout ledger tracking.
- **Pilot Payouts** — capture and sync payout rates without opening KML Generator.
- **Aircraft suitability** — pick an aircraft and set its fuel and payload, and every airport in the app is checked against it: an airport only counts as suitable if a single runway is long enough for the aircraft to both land there *and* take off again at that load, with the surface type, SimFly category, and the airport's density altitude all factored in. Hovering any airport code shows the takeoff and landing distances it needs, and says which of the two falls short when an airport doesn't qualify. The Balance Queue can be filtered down to just the pilots you can actually reach.
- **Plan Flight → Active Airports** — pick a departure/arrival pair and hand the route straight to [Active Airports](https://kyndrarocks.github.io/SimFlyActiveAirports/) for flight planning.

---

Public repo: https://github.com/KyndraRocks/SimFlyRecipTracker
