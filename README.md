# SimFly Recip Tracker

A single-file reciprocation-tracking tool for SimFly airport owners. Tracks which pilots have flown to your airports, scores them by how overdue a return visit is, manages a welcome queue for new pilots, and hands off routes to Active Airports for flight planning.

**Current version: v2.69.0**

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

The Gist is the source of truth, so connecting from a new device brings your full history with it. Files of any size are read in full, unreadable Gist data is never treated as empty, and any save that would sharply shrink your stored history is refused rather than written.

---

## Features

- **Balance Queue** — prioritizes which pilots to fly back to, scored by how overdue and how loyal each pilot is. Every row is a bar chart growing out from a centre line — their inbound visits to you on the left, your outbound returns to them on the right — so the balance of a relationship reads at a glance, in the same order as the inbound:outbound Ratio printed beside it. Click any column to sort by it; clicking another column stacks it underneath as a tiebreaker, so you can order the queue by Opportunity and break ties by how long it has been since you last flew to someone. How you leave the queue is how you find it — the sort, every filter, and the date-range slider that sets how far back it looks are all remembered between visits. Rows carry tags for the departure and arrival pilots of the route you are planning, and for pilots you have just flown to or sent to the map; a long pilot name shortens rather than crowding those tags off the row.
- **Pilot activity** — the queue also knows how much each pilot actually flies, drawn from SimFly's public Sky Ranking. An **Activity** column shows their flight count over a window — 7, 30 or 90 days, or their whole career — and a **Flights** column gives their all-time career total. Read together they separate a pilot worth cultivating from one who used to be busy and has since gone quiet — flying a return leg to someone who has stopped playing earns nothing back. Two filters follow from it: show only pilots active at least N times in the window, or with at least N flights all-time. By default the window follows the date-range slider on its own, snapping to whichever board best matches the span you are looking at; whichever window is live is outlined, and you can pin one by hand instead. It follows rather than matches the slider because SimFly publishes fixed activity boards — 24-hour, 7-day, 30-day and all-time — rather than dates for individual flights, so a figure for an arbitrary span like the last 45 days is not something that can be worked out. For the same reason the 90-day figure is assembled here from daily snapshots rather than fetched, so it deepens over time and says how much history stands behind it. The all-time window is an experience floor rather than a recency check: a career total never falls, so it cannot tell a pilot who stopped flying last year from one who flew this morning.
- **Opportunity score** (optional) — one 0–100 column answering “who is worth flying to next”. It combines how loudly a relationship asks for attention (visits owed, and how overdue you are) with how likely a return flight is to bring future traffic back (their activity), and it multiplies the two rather than adding them — so a dormant pilot scores near zero however many visits they owe. Hovering a score shows exactly how it was reached, and three sliders, each running 0 to 5, let you steer the balance. The one with the most reach is how harshly to discount pilots who have gone quiet: by default it scales straight in proportion to how much they fly, so an occasional flyer still ranks clearly ahead of an abandoned account, and turning it up separates the steady flyers from the merely occasional — at the maximum, someone flying half as often as a fully active pilot keeps well under a tenth of their score. Each window sets its own bar for what counts as fully active — 14 flights in 7 days, 60 in 30, 180 in 90, or 800 across a career, roughly two a day — and anyone at or above it is treated as equally reachable, so the score concentrates on telling apart the pilots below that line. The other two, how much being owed visits matters against how much being overdue matters, are weighed against each other, so only the balance between them changes the queue. Off by default; the other columns stay raw counts.
- **Flight history** — expanding a pilot's row draws their whole back-and-forth with you as a chart: inbound visits and your outbound flights on one timeline, thirty days in view at a time and scrollable back through the full history. Hovering anywhere on it snaps a crosshair to the nearest day and reports that date with both counts.
- **Flight Impact** — after you log a return flight, a panel shows exactly what it changed: before → after for the pilot's outbound count, balance owed, ratio, last-reciprocated date, Opportunity score and position in the queue — a card for each pilot when a flight credits both the departure and arrival owner. If the flight pushes a pilot out of the queue because one of your filters no longer matches them, it says so rather than leaving them to vanish. Reciprocated pilots keep a highlight and a badge on their row for a quarter of an hour so you can find them again.
- **Quick Entry** — fast logging of inbound flights from your SimFly PAX wallet log.
- **Welcome Queue** — tracks new pilots who've flown in and haven't been welcomed yet.
- **Pilot Directory** — searchable roster of every tracked pilot and their airports.
- **Dashboard** — reciprocation history, filters, and CSV export.
- **Wallet** — SimFly PAX payout ledger tracking.
- **Backup** — one click in the top bar downloads a dated JSON snapshot of every pilot and every inbound and outbound flight, so a copy of your history exists outside GitHub.
- **Pilot Payouts** — capture and sync payout rates without opening KML Generator.
- **Aircraft suitability** — pick an aircraft and set its fuel and payload, and every airport in the app is checked against it: an airport only counts as suitable if a single runway is long enough for the aircraft to both land there *and* take off again at that load, with the surface type, SimFly category, and the airport's density altitude all factored in. Hovering any airport code shows the takeoff and landing distances it needs, and says which of the two falls short when an airport doesn't qualify. The Balance Queue can be filtered down to just the pilots you can actually reach.
- **Plan Flight → Active Airports** — pick a departure/arrival pair and hand the route straight to [Active Airports](https://kyndrarocks.github.io/SimFlyActiveAirports/) for flight planning.

---

Public repo: https://github.com/KyndraRocks/SimFlyRecipTracker
