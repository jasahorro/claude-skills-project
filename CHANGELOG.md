# Changelog — claude-skills-project

## Commit History

Oldest first:

- `c7ac83e` feat: add greeting app (24 minutes ago)
- `c0e4ec5` docs: add CHANGELOG.md (16 minutes ago)
- `0824e84` docs: update CHANGELOG.md with latest history (2 minutes ago)
- `a8e0dc1` feat(app): add multiply function (just now)

## Working Tree Status

Clean. There are no uncommitted changes.

## Tracked Files

- `app.py`: A small Python script with `greet(name)`, which returns a welcome message, plus `add(a, b)` and `multiply(a, b)` for simple arithmetic. When run directly, it prints all three results.
- `.claude/skills/smart-commit/SKILL.md`: A Claude Code skill that stages all changes and commits them with a conventional commit message.
- `.claude/skills/changelog/SKILL.md`: A Claude Code skill that regenerates `CHANGELOG.md` from the git history.
- `.claude/skills/dev-pipeline/SKILL.md`: A Claude Code skill that runs smart-commit and then changelog in one step.
- `CHANGELOG.md`: This file. It lists the project's commit history, working tree status, and tracked files.
