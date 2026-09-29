# myskills

Personal skills packaged for Codex and Claude Code. Add skill folders under `plugins/myskills/skills/`; the repository currently contains only a starter template.

## Install

Claude Code:

```sh
claude plugin marketplace add .
claude plugin install myskills@myskills
```

Codex: add this repository as a plugin marketplace with `codex plugin marketplace add .`, then enable `myskills` from the Plugins directory.

## Add a skill

Copy `plugins/myskills/templates/SKILL.md` to `plugins/myskills/skills/<skill-name>/SKILL.md` and fill it in. Keep platform-specific configuration alongside the skill only when needed.
