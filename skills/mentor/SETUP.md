# Project setup

Two pieces turn mentor mode on automatically in a repo. Propose both to the
maintainer when either is missing; add them only with their approval, and
follow the repo's commit rules.

## 1. `Mentoring` section in `AGENTS.md`

Add to the repo's `AGENTS.md` (or `CLAUDE.md` if there is no `AGENTS.md`):

```md
## Mentoring

- If `~/.learning/profile.md` exists, the person is a learner: run every coding
  task through the `mentor` skill. Anyone can start with `/mentor`.
- Project risk zones, on top of the skill's defaults: {risk zones}.
```

Fill `{risk zones}` by reading the repo: name the concrete files, tables, or
flows where a bug loses money, data, or trust (the auth callback, the payment
webhook, `migrations/`, the job that sends emails). Name things a teammate can
find; skip generic categories the skill already covers.

## 2. Session-start hook (Claude Code)

Merge into the repo's `.claude/settings.json`, keeping any existing hooks:

```json
{
  "hooks": {
    "SessionStart": [
      {
        "hooks": [
          {
            "type": "command",
            "command": "if [ -f \"$HOME/.learning/profile.md\" ]; then echo 'Learner profile found at ~/.learning/profile.md: run every coding task through the mentor skill.'; fi"
          }
        ]
      }
    ]
  }
}
```

The hook makes the trigger deterministic in Claude Code; the `AGENTS.md` line
covers other agents.
