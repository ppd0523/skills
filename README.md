# skills

Skills for Codex and Claude Code. Add skill folders under `skills/`; the repository currently contains the `git-commit` skill and a starter template.

## Install

Codex:

```sh
codex plugin marketplace add ppd0523/skills
codex plugin add skills@skills
```

Install a skill with npx:

```sh
npx skills@latest add ppd0523/skills --skill git-commit
```

Claude Code:

```sh
claude plugin marketplace add ppd0523/skills
claude plugin install skills@skills
```

## Add a skill

Copy `templates/SKILL.md` to `skills/<skill-name>/SKILL.md` and fill it in. Keep platform-specific configuration alongside the skill only when needed.
