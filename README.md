# team-skills

A Claude Code plugin marketplace with the skills we share across projects.

## Mentor mode (`peshang` plugin)

Learn to code while building real products. The agent places each learner on a
level per area (UI, server, database, testing, tooling), then teaches through
the project's own test cycles: the learner predicts, writes, and runs the code,
with help scaled to their level. Risky code (auth, payments, migrations,
personal data) stays at Pair level or below. Progress lives privately in each
learner's `~/.learning/`, so it follows them across repos and is never
committed.

### Turn it on in a project

Open the project in Claude Code and ask: "set up peshang:mentor for this repo".
The agent proposes the two committed pieces from
[SETUP.md](skills/mentor/SETUP.md): the plugin entry in `.claude/settings.json`
and a `Mentoring` section in `AGENTS.md` with the project's risk zones.

After that, every teammate who opens the repo and trusts the folder gets the
plugin. Claude Code fetches it in the background on the first session, so that
first time, run `/reload-plugins` (or start a new session) once it says
"Plugins changed". If it never appears, run
`/plugin marketplace add peshang72/team-skills` in the repo.

Then check `/plugin` → Marketplaces → team-skills shows auto-update on; if not,
select **Enable auto-update** once.

### Start learning

In a project that has it, open a new session and run `/peshang:mentor`. The first
run is a 15-minute placement check; after that, every session in mentor-enabled
repos runs in mentor mode. Say "deadline" to get one task done fast and review
it later.

### Ship a change

Edit, commit, and push. Teammates pick it up automatically: Claude Code checks
for updates a few minutes into each session, and the new version loads on the
next launch (or after `/reload-plugins`). There is no version number to bump;
updates follow the commits.
