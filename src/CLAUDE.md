# Source layer — Claude Code scope

Rules for work under `src/` (CLI commands, core logic, utilities).

## Layout

- `cli.ts` — commander entry; register new subcommands here
- `commands/` — one file per user-facing command
- `core/` — template engine, linter, project detector (inject deps for tests)
- `utils/` — fs, paths, logger, errors, ui

## When editing here

Follow ESM imports with `.js` extensions. Shared types belong in `src/types.ts`.

@import ../claude/cli-conventions.md
