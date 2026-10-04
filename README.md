# Square

A 27-minute timer drawn as an 81 × 81 square of lamps: 3⁸ = 6561 of them,
one per 1/243 of a minute, filled in nested base-3 order. A 3 × 3 block is
1/27 of a minute, 9 × 9 is twenty seconds, 27 × 27 is three minutes, and
the full square is the session.

The trimmed-down successor to [Salvation](https://github.com/inersphobia/Salvation).
It has no build step and no dependencies: one `index.html`, a manifest and a service worker.

## Use

- A session is always 27 minutes.
- **1/9** switches the square to a ninth of the session: it fills every
  3 minutes, nine times over (one lamp per 1/2187 of a minute), and a row
  of nine lamps labelled in base 3 (10, 20, 100 … 1000, i.e. 3 to 27
  minutes) counts the 3-minute squares you've
  finished. It's only a view, so you can switch it mid-session.
- **START / PAUSE / RESUME**. When the session finishes, a bell rings and
  overtime counts up in amber, also in base 3: `+12:2000₃` is 5 minutes
  (12₃) and two thirds of a minute (:2000₃).
- **RESET** closes the session and asks for a verdict: **T** and **P**,
  each − / 0 / +, plus an optional note. SKIP saves it unrated; BACK
  returns to the paused timer. Anything under a minute is discarded.
- **SCORE** shows today, this week and this month, with history by
  day, week or month. A session scores T + P, and a period's score is the
  sum of its sessions. Tap a row to see its sessions. EXPORT downloads
  everything as JSON.

The readout is base 3: three places for the minute within the current
square, a colon, then four places for thirds, ninths, 27ths and 81sts of a
minute. Each digit is two lamps: none lit is 0, one is 1, two is 2.

## Install

Open **https://inersphobia.github.io/salv3/** on the phone, then use
*Add to Home Screen* (Safari's Share menu, or Chrome's ⋮ menu).

It is published by GitHub Pages from `main` (Settings → Pages → Deploy from a branch).

## Data

Everything stays in the browser's `localStorage`. On first launch, sessions
from the old Salvation app are imported when both apps share an origin
(e.g. both on `inersphobia.github.io`). The old data is only read, never changed.
