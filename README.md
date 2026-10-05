# Square

A 27-minute timer drawn as an 81 × 81 square of lamps: 3⁸ = 6561 of them,
one per 1/243 of a minute, filled in nested base-3 order. A 3 × 3 block is
1/27 of a minute, 9 × 9 is twenty seconds, 27 × 27 is three minutes, and
the full square is the session.

The trimmed-down successor to [Salvation](https://github.com/inersphobia/Salvation).
It has no build step and no dependencies: one `index.html`, a manifest and a service worker.

## Use

- A session is always 27 minutes.
- The **view key** (three small lights) cycles three views of it:
  - **one light:** 81 × 81 = 6561 lamps, one per 1/243 of a minute; the
    square is the whole session.
  - **two lights:** 27 × 27 = 729 lamps, one per 1/27 of a minute (about
    2.2 s); the square is the whole session.
  - **three lights:** 27 × 27 = 729 lamps, one per 1/81 of a minute (the
    readout's fastest digit), so the square fills in 9 minutes, three
    times over.

  It's only a view, so you can switch it mid-session; the frame around
  the square is the same in all three.
- **▶ / ❚❚** starts, pauses and resumes. When the session finishes, a bell
  rings and overtime counts up in amber, also in base 3: `+12:2000₃` is
  5 minutes (12₃) and two thirds of a minute (:2000₃).
- **↺ (reset)** closes the session and asks for a verdict: **T** and **P**,
  each − / 0 / +, plus an optional note. SKIP saves it unrated; BACK
  returns to the paused timer. Anything under a minute is discarded.
- **LOGS** shows today, this week and this month, with history by
  day, week or month. A session scores T + P, and a period's score is the
  sum of its sessions. Tap a row to see its sessions. EXPORT downloads
  everything as JSON.

The time is base 3. Below the square, the readout has three places for the
minute of the session (000 to 222), a colon, then four places for thirds,
ninths, 27ths and 81sts of a minute. Each digit is two lamps: none lit is
0, one is 1, two is 2. Above the square, three lamps labelled 100,
200 and 1000 (9, 18 and 27 minutes) are always shown, but they light
only in the three-light view: there each turns amber as its nine minutes
finish, standing in for the readout's nines digit, which stays dark.

## Install

Open **https://inersphobia.github.io/salv3/** on the phone, then use
*Add to Home Screen* (Safari's Share menu, or Chrome's ⋮ menu).

It is published by GitHub Pages from `main` (Settings → Pages → Deploy from a branch).

## Data

Everything stays in the browser's `localStorage`. On first launch, sessions
from the old Salvation app are imported when both apps share an origin
(e.g. both on `inersphobia.github.io`). The old data is only read, never changed.
