# Learner state formats

## Profile

`~/.learning/profile.md`. One per learner, shared across every repo. Keep it
under a screen.

```md
# Learner profile

- Name: Aram
- GitHub: aram-dev
- Explanation language: ckb
- Goal: Build and ship a full feature on my own by April 2027.
- Time: 6 hours a week
- Learns best by: trying first, then reading

## Levels

| Area | Level | Focus | Since |
|---|---|---|---|
| ui | 1 Guided | yes | 2026-10-16 |
| server | 0 Observer | yes | 2026-10-16 |
| database | 0 Observer | yes | 2026-10-16 |
| testing | 1 Guided | yes | 2026-10-16 |
| tooling | 1 Guided | yes | 2026-10-16 |
| ux | 0 Observer | no | 2026-10-16 |
| visual | 1 Guided | no | 2026-10-16 |

## Preferences

- Prefers diagrams for data flow.
```

Areas, for web apps:

- **ui** — components, pages, styling, forms, client state
- **server** — routes, server actions, validation, background jobs, external APIs
- **database** — schema, queries, migrations, transactions
- **testing** — writing and reading unit, integration, and end-to-end tests
- **tooling** — terminal, git, package manager, debugging, reading errors
- **ux** — users, jobs, flows, usability testing
- **visual** — layout, spacing, type, colour, hierarchy, critique of generated UI

Add an area when a project needs one these don't cover (e.g. `mobile`).

**Focus** is set from the goal at onboarding: `yes` for the areas the goal is
about, `no` for the rest. The learner can switch an area's focus anytime; its
level is already placed. A design goal focuses `ux`, `visual`, `ui`, and
`tooling`; a coding goal focuses the five code areas.

## Records

`~/.learning/records/NNNN-slug.md`. Number = highest existing + 1. Create the
folder when writing the first one.

```md
---
area: server
project: hair-salon
demonstrated: yes
next_review: 2026-10-18
interval: 2
---

# Validating input at the route boundary

Wrote the schema for the booking request unaided and explained why inner code
can trust typed data after it. Unlocks: writing new routes at Pair level.

Review: Why validate at the boundary instead of inside each function?
```

- **One thing per record**, in 1–3 sentences, saying what it unlocks next.
- `demonstrated: no` marks a concept seen but not yet shown (deadline mode, or a
  misconception just corrected). Answering its review correctly flips it to `yes`.
- `project` matters for codebase-specific knowledge; use `general` for concepts
  that transfer (closures, SQL joins).
- **Review** is a recall question answerable from memory, asking *why* or *what
  happens*, not a definition.
- When understanding is later corrected, add `superseded_by: NNNN` to the old
  record instead of deleting it.
- `ux` and `visual` records carry a `source:` field: the link (or book and
  chapter) for the cited principle, so a warm-up review can point back to it.
- A **wrong usability prediction** is a record: what the learner expected, what
  people actually did, and why. Its review question gives a similar scenario
  and asks them to predict.

## Usability files

`~/.learning/usability/YYYY-MM-DD-slug.md`. Written at the UX pass, before
building, so predictions can't drift to match what happened; finished when the
learner brings back test notes, which may be sessions later.

```md
---
project: hair-salon
feature: rebook from the confirmation email
status: untested
participants: target users
---

## Task
You booked a haircut last month. Book the same haircut again for next Friday.

## Predictions
- People will miss the "rebook" link below the receipt.

## Notes
(the learner's notes from each session)

## Debrief
(each prediction: right or wrong, and why)
```

- `status`: `untested` → `tested` once the debrief is written.
- `participants`: `target users`, or `teammates` (weaker evidence).

## Spacing

After a warm-up review question:

- Correct → double `interval` (start at 1: 1 → 2 → 4 → 8 … days, max 60) and set
  `next_review` = today + `interval`.
- Wrong or partly wrong → explain briefly, set `interval` to 1 and `next_review`
  to tomorrow.
