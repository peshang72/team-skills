# team-skills

A Claude Code plugin marketplace with the skills we share across projects.

## Install

The marketplace is `team-skills` and it ships one plugin, `peshang`.

### For yourself, in every project

In any Claude Code session, run:

```
/plugin marketplace add peshang72/team-skills
/plugin install peshang@team-skills
/reload-plugins
```

Or from a shell:

```sh
claude plugin marketplace add peshang72/team-skills
claude plugin install peshang@team-skills
```

To get updates automatically, open `/plugin` → Marketplaces → team-skills and
select **Enable auto-update**. To update by hand, run
`/plugin marketplace update team-skills`. To remove it, run
`/plugin uninstall peshang@team-skills`.

### For a whole team, in one repo

Commit the plugin to the repo's `.claude/settings.json` so every teammate gets
it when they trust the folder:

```json
{
  "extraKnownMarketplaces": {
    "team-skills": {
      "source": { "source": "github", "repo": "peshang72/team-skills" },
      "autoUpdate": true
    }
  },
  "enabledPlugins": {
    "peshang@team-skills": true
  }
}
```

Merge these keys into any settings already there. For mentor mode the repo also
needs a `Mentoring` section in `AGENTS.md`; see
[Turn it on in a project](#turn-it-on-in-a-project) below.

### Check it worked

Run `/plugin` and look for `peshang` under Installed, or type `/peshang:` and
check that `/peshang:mentor` is offered.

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
