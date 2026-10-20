# Design cycles (`ux` and `visual`)

Read when the task touches a focus area `ux` or `visual`. Everything in
[SKILL.md](SKILL.md) still applies — levels, predictions, records, deadline
mode; this file says what a cycle looks like when the work is design.

- **ux** — who the user is, the job they're doing, the flow, usability.
- **visual** — layout, spacing, type, colour, hierarchy, states, and critique of
  generated UI.

## Sources, never memory

Every design principle you teach is **cited**: a link to a source on the
allowlist and a short quote. Teach from a reviewed explainer in
`docs/learn/design/` when one covers the principle; otherwise fetch the source
and cite it live. Can't fetch it → say so and leave that principle untaught.
Allowlist and explainer rules: [SOURCES.md](SOURCES.md).

## Where design work comes from

- **UX pass before building.** Before the first red → green cycle of any
  feature users touch, settle: the user, the job they're doing, a flow sketch,
  and the learner's **predictions** of where users will stall. Write the
  predictions into a usability file (see [FORMATS.md](FORMATS.md#usability-files))
  now, before anything is built.
- **Design tasks** (interviews, flow audits, a screen redesign) can be chosen in
  step 3 like any other task.

## Alternatives

Explore 2–3 alternatives before building, while they're cheap to throw away.
Below Pair, you make them as throwaway HTML with the `prototype` skill and the
learner predicts which works best for users and why. At Pair and above, the
learner makes them — in code, or in Figma shared as screenshots — and you
critique.

## The cycle

Each cycle runs the [SKILL.md](SKILL.md#4-build-in-cycles) shape — explain just
in time, learner acts, predict, run — with these as the **run**:

1. **Automated checks** — the design's red → green: colour contrast, axe
   accessibility, Lighthouse. Use the project's own checks if it has them;
   otherwise run axe and Lighthouse against the dev server.
2. **Heuristic review** — check the screen against named heuristics from the
   sources. The learner predicts the issues first; you name each one with its
   cited principle.
3. **Before/after** — screenshot the screen before and after a visual change
   (the `run` skill, or the learner pastes them). The learner predicts what the
   change fixes; you critique the after-shot, each point cited.

## Closing a feature: test with people

The honest loop for design is watching real people. When the feature works:

1. The learner runs a **usability test** (3–5 people, the task from the
   usability file) and a **5-second test** (what did they notice first?).
   Target users count as evidence; teammates count as weaker evidence — mark
   which in the file.
2. The learner brings back notes. **Debrief** them against the written
   predictions: every gap between prediction and what people did is a lesson,
   and a wrong prediction becomes a record (see [FORMATS.md](FORMATS.md#records)).
3. No test run → set the usability file's `status: untested` and say so in the
   maintainer line. The test can happen in a later session.

## Levels

### ux

| Level | Agent | Learner |
|---|---|---|
| 0 Observer | Does the UX pass and cites sources | Predicts where users will struggle; names the principle behind one issue per cycle |
| 1 Guided | Drafts the flow and critique, leaving named gaps | Writes the job statement, finds 2+ issues, writes the usability-test task |
| 2 Pair | Asks, points to sources, debriefs | Writes the flow, predictions and test script; runs the test |
| 3 Independent | Reviews against sources | Runs the whole UX loop and chooses what to research |

### visual

| Level | Agent | Learner |
|---|---|---|
| 0 Observer | Improves the screen in code | Predicts what each change fixes; names the principle behind one change per cycle |
| 1 Guided | Improves the screen, leaving named gaps | Fills the gaps: a spacing value, a contrast fix, a heading size, an empty state |
| 2 Pair | Critiques with sources | Restyles screens in code; makes alternatives in code or Figma |
| 3 Independent | Reviews against sources | Owns the visual decisions, including the app's type, spacing and colour system |

## Design risk zones

Mistakes here hurt users or break the law. The learner works at **Pair at
most**, and every decision cites a source:

- accessibility (cite W3C WAI / WCAG)
- consent, privacy notices, and dark patterns
- checkout, payment, and booking-confirmation flows
- destructive or irreversible actions (delete, cancel)
