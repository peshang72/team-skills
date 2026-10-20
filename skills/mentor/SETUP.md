# Project setup

Two committed pieces turn mentor mode on in a repo. Propose both to the
maintainer when either is missing; add them only with their approval, and
follow the repo's commit rules.

## 1. Enable the plugin in `.claude/settings.json`

Merge into the repo's `.claude/settings.json`, keeping existing keys:

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

Teammates get the plugin, its session-start hook, and its updates once they
trust the folder. The hook ships inside the plugin, so the repo needs no hook
of its own; remove any older copy of it.

## 2. `Mentoring` section in `AGENTS.md`

Add to the repo's `AGENTS.md` (or `CLAUDE.md` if there is no `AGENTS.md`):

```md
## Mentoring

- If `~/.learning/profile.md` exists, the person is a learner: run every coding
  task through the `peshang:mentor` skill, including tasks started with another
  skill. Anyone can start with `/peshang:mentor`.
- Project risk zones, on top of the skill's defaults: {risk zones}.
```

Fill `{risk zones}` by reading the repo: name the concrete files, tables, or
flows where a bug loses money, data, or trust (the auth callback, the payment
webhook, `migrations/`, the job that sends emails). Name things a teammate can
find; skip generic categories the skill already covers.

## Optional: a welcome note for a new learner

Nothing personal goes in the repo. To greet a new learner, the maintainer puts
`~/.learning/welcome.md` on the learner's machine before their first session:

```md
---
for: <learner's GitHub login>
from: <maintainer>
---
What you'd like the mentor to tell them, in a sentence or two.
```

Onboarding passes it on in its own words once the login matches, then deletes
the file. If the learner places the file themselves, they'll read it first.
