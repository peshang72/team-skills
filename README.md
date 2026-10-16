# team-skills

Agent skills shared across our projects.

## mentor

Learn to code while building real products. The agent places each learner on a
level per area (UI, server, database, testing, tooling), then teaches through
the project's own test cycles: the learner predicts, writes, and runs the code,
with help scaled to their level. Risky code (auth, payments, migrations,
personal data) stays at Pair level or below. Progress lives privately in each
learner's `~/.learning/`, so it follows them across repos and is never
committed.

### Add it to a project

```sh
npx skills add peshang72/team-skills --skill mentor
```

Then, in that project, ask the agent to "set up mentor for this repo". It adds
a `Mentoring` section to `AGENTS.md` with the project's risk zones, plus a
session-start hook that switches mentor mode on for learners
([SETUP.md](skills/mentor/SETUP.md)).

### Start learning

In any project that has it, open a new session and run `/mentor`. The first
run is a 15-minute placement check; after that, every session in mentor-enabled
repos runs in mentor mode. Say "deadline" to get one task done fast and review
it later.

### Update

```sh
npx skills update mentor
```
