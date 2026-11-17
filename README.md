# SafaiKit — Your Home, Sparkling on Schedule

A calm home-cleaning planner that turns housework into a plan instead of a nagging list. One single self-contained HTML file — no backend, no signup, everything saved on your device.

**Live:** https://abhiramunni.github.io/safaikit/

## What it does

- **The floor plan** — five rooms (Kitchen, Bathroom, Bedroom, Living Room, Balcony) drawn as a house plan. A room glows terracotta when something in it is overdue. Tap a room to open its chore list.
- **Today's clean** — a progress ring and a list of everything due today, overdue first. Tick a chore and SafaiKit schedules its next round automatically (daily, every 2 days, weekly, fortnightly or monthly).
- **The week ahead** — a 7-day strip showing how many chores land on each day. Tap a day to see exactly what lands on it.
- **Deep-clean calendar** — six big monthly jobs (chimney filter, curtains, mattress, fan blades, kettle, shower curtain), spread across the month so no weekend is ruined.
- **The 15-minute blitz** — a countdown timer for when guests are coming, with quick-win chore suggestions.
- **Supply cupboard** — cleaning supplies with in-stock / running-low flags, so you never run out of floor cleaner mid-mop.
- **The rota** — chores shared across flatmates, with a one-tap rotate that hands every chore to the next person.
- **Clean smarter, not harder** — six plain-language guides (vinegar for hard-water stains, the pillowcase fan trick, descaling a kettle, stopping monsoon mould, homemade all-purpose spray, the 10-minute nightly reset).
- **Streak** — counts consecutive days with every daily chore done.
- **Copy summary** — a WhatsApp-friendly text summary of today's cleaning state.

## Seeded example data

The app ships with 29 sample chores across the five rooms, 8 supplies and 6 deep-clean jobs, so the floor plan, rings and rota are alive on first open. Every sample is marked and removable in one tap (**Remove sample chores**); your own additions are never touched by that button. **Erase everything** (two-tap) wipes the app back to a blank slate.

## How the scheduling works

Each chore has a rhythm in days and a "last done" date. The next due date is last done + rhythm. A chore is **due** when its next due date is today or earlier, and **overdue** when that date has passed. Ticking a chore sets its last done to today, which pushes the next round out automatically. Dates are stored as local calendar dates, so nothing shifts across timezones.

## Design

Warm editorial palette (ivory paper, espresso ink, bronze / amber / gold / terracotta), Fraunces + Inter, a full-screen cinematic intro with tap-to-skip (quick version on return visits), a 3-step onboarding tour, Ken Burns drift on the two AI-generated photos, and inline SVG icons throughout. No emoji, no external images.

## Privacy

All data lives in `localStorage` under the key `safaikit-v1`. Nothing is sent to any server. The only network request is the Google Fonts stylesheet.

## Running it locally

Open `index.html` in any modern browser. No build step.

## QA

Headless jsdom suite in `qa-test.js`: 65/65 assertions pass, `node --check` clean, zero uncaught JS errors. It covers due-date maths (11 due today, 4 overdue, streak of 5), room stats, intro/coach flow, ticking, room-sheet CRUD, week filtering, deep-clean toggles, supply toggles, rota rotation, the blitz timer, copy summary, sample removal and the two-tap erase.
