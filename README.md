# Santorini Bus — Pocket Guide (August 2026)

A single-file, offline-capable guide to the KTEL Santorini public bus network, written for
travelers from the United States.

**The file you want is [`santorini-bus-guide.html`](santorini-bus-guide.html).** Open it in any
browser. That is the whole thing — there is nothing to install, no build step, and no server.

## What's in it

| Section | What it does |
| --- | --- |
| Next bus, right now | Reads the official timetable against the current clock **in Santorini** and tells you the next departure and the eight after it |
| Last bus home | Always-visible countdown to the final departure back to Fira from wherever you are, colour-coded green / amber / red, with the Fira taxi rank number once it has gone |
| The mental model | The hub-and-spoke diagram: every route ends at Fira, so every trip is one ticket or two |
| Official fares | Every fare from the KTEL sheet — nearly everything is €2.20, with three €2.70 exceptions |
| Full timetables | All ~230 published departures, both directions, with EXP and ΣΧ markings decoded |
| Cost calculator | Pick two points, get the legs, the ticket count, the total in euros and dollars |
| Where to stand | Addresses, coordinates and landmark descriptions for every stop |
| When the bus fails you | The four situations that strand people, and how to avoid them |
| Briefing for U.S. travelers | Cash-only rules, ATM advice, 24-hour clock, EES/ETIAS entry status, tipping |
| Put this on your phone | Step-by-step for adding a home-screen icon and saving an offline copy |

## Where the data comes from

Every fare and departure time is transcribed from the **official KTEL Santorini timetable and
fare sheet, revised 14 July 2026** — included here as
[`ktel-santorini-timetable-2026-07-14.pdf`](ktel-santorini-timetable-2026-07-14.pdf).

This matters, because popular travel sites currently disagree with the official sheet:

| Claim found on travel sites | Official KTEL sheet |
| --- | --- |
| Last Oia → Fira bus is 21:20 | **22:50** |
| Monolithos costs €1.60, last bus 17:00 | **€2.20**, last bus 21:10 |
| Kamari costs €1.80 | **€2.20** |
| Pyrgos / Megalochori / Emporio cost €2.50 | **€2.20** |
| Fira → Airport takes 15–20 min | **10 min** (printed on the sheet) |
| Fares range €2.20–€2.80 | Exactly two prices: **€2.20**, or **€2.70** for Athinios Port, Perissa and Vlychada |

Non-timetable facts — taxi price comparisons, ATM and payment practice, EES/ETIAS entry status —
are sourced separately and cited in the page footer.

Run times not printed on the sheet are derived from the published outbound/return offsets (e.g.
Akrotiri departs Fira at 10:00 and departs Akrotiri at 10:20, so the run is 20 minutes). The
Perissa figure is an estimate, since that route has no clean paired offset. This is stated on the
page.

## Offline by design

No fonts, scripts, styles, or images are fetched from the network. The timetables and the
next-bus logic are plain JavaScript inside the file. It works in airplane mode.

The clock uses `Intl.DateTimeFormat` with `timeZone: "Europe/Athens"`, so departure countdowns are
correct whether the device is set to Santorini time or to a U.S. time zone.

**Install the downloaded file, not a bookmark.** On Android: save the file, open it from *My Files
→ Downloads* in Chrome, then ⋮ → *Add to Home screen*. Verify by switching on airplane mode and
tapping the icon.

It deliberately does **not** self-update. A `file://` page cannot fetch remote content, and the
underlying KTEL sheet is a seasonal revision rather than a live feed, so there is nothing to sync.
To refresh, re-download the file over the old one; the home-screen icon picks up the new copy.

## Verify before you rely on it

Greek island schedules are revised in-season with ferry traffic and demand. For anything
time-critical — a flight, a ferry, a booked tour — check the printed board inside Fira Central Bus
Station, or call KTEL Santorini on **+30 22860 25404**.
