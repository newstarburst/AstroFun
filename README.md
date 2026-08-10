# Santorini Bus

A one-screen trip planner for the KTEL Santorini public bus network. Say where you are and where
you're going; it tells you which bus, when, where to stand, and what it costs.

**[`santorini-bus-guide.html`](santorini-bus-guide.html)** — this is the app. Open it in any
browser. One file, no build step, no server, no network.

## What it does

Pick a start and a destination. It answers with:

- **Catch the bus at 14:20, in 20 min** — read against the live clock in Santorini
- **Numbered steps** — which bus, where to wait, how long the ride is, when to change and pay again
- **The price** in euros and dollars, and how many tickets you actually need
- **Last bus back to Fira**, colour-coded green / amber / red, with the taxi rank number once it's gone
- **Later departures**, if you'd rather not rush

Transfers are planned against the real timetable, not a guess: it takes your actual arrival time in
Fira, allows five minutes to walk between bays, and finds the next connecting departure.

Everything else lives behind one collapsed **Need to know** panel — cash only, pay per bus, kids'
fares, phone numbers.

## Also here

[`santorini-full-guide.html`](santorini-full-guide.html) — the long-form reference version:
network diagram, complete fare table, all ~230 published departures, worked trip budgets, and a
briefing for U.S. travelers (cash and ATM practice, 24-hour clock, EES/ETIAS entry status). Useful
for planning, too much for standing at a bus stop.

## Where the data comes from

Every fare and departure time is transcribed from the **official KTEL Santorini timetable and fare
sheet, revised 14 July 2026** — included as
[`ktel-santorini-timetable-2026-07-14.pdf`](ktel-santorini-timetable-2026-07-14.pdf).

This matters, because popular travel sites disagree with the official sheet:

| Claim found on travel sites | Official KTEL sheet |
| --- | --- |
| Last Oia → Fira bus is 21:20 | **22:50** |
| Monolithos costs €1.60, last bus 17:00 | **€2.20**, last bus 21:10 |
| Kamari costs €1.80 | **€2.20** |
| Pyrgos / Megalochori / Emporio cost €2.50 | **€2.20** |
| Fira → Airport takes 15–20 min | **10 min** (printed on the sheet) |
| Fares range €2.20–€2.80 | Two prices: **€2.20**, or **€2.70** for Athinios Port, Perissa and Vlychada |

Run times not printed on the sheet are derived from the published outbound/return offsets (Akrotiri
leaves Fira at 10:00 and leaves Akrotiri at 10:20, so the run is 20 minutes). The Perissa figure is
an estimate — that route has no clean paired offset.

Athinios Port has no clock timetable at all; KTEL schedules it against the ferry manifest. The app
says so rather than inventing times.

## Offline by design

Nothing is fetched from the network — no fonts, scripts, styles or images. It works in airplane
mode.

The clock uses `Intl.DateTimeFormat` with `timeZone: "Europe/Athens"`, so countdowns are correct
whether the phone is set to Santorini time or a U.S. time zone.

**Install the downloaded file, not a bookmark.** On Android: save it, open from *My Files →
Downloads* in Chrome, then ⋮ → *Add to Home screen*. Verify by turning on airplane mode and tapping
the icon.

It deliberately does **not** self-update: a `file://` page cannot fetch remote content, and the KTEL
sheet is a seasonal revision rather than a live feed. To refresh, re-download over the old file.

## Verify before you rely on it

Greek island schedules shift in season with ferry traffic and demand. For anything time-critical,
check the printed board inside Fira Central Bus Station or call KTEL on **+30 22860 25404**.
