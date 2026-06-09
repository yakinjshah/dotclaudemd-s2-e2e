# Plan mode vs direct execution (Scenario 2 step 5)

Evidence from using Claude Code on this repo.

## Direct execution — tiny fix

**Task:** Fix a typo in a log string inside `src/utils/logger.ts`.

**Mode:** Direct (no plan). Claude edited the one line immediately.

```bash
claude
# Prompt: "In src/utils/logger.ts change the debug prefix from [dotclaudemd] to [dotclaudemd:debug]."
```

**Why direct:** Single-file, obvious change; planning would add overhead.

## Plan mode — multi-file feature

**Task:** Add a `dotclaudemd validate` subcommand that wraps lint + doctor.

**Mode:** Plan first (`Shift+Tab` / `/plan` depending on Claude Code version).

```bash
claude --plan
# Prompt: "Design dotclaudemd validate: runs lint then doctor, exits non-zero on errors. List files to touch before editing."
```

**Plan output (saved here):**

1. Add `src/commands/validate.ts` calling existing linter and doctor-check modules.
2. Register subcommand in `src/cli.ts`.
3. Add vitest coverage under `tests/commands/validate.test.ts`.
4. Document command in README Commands section.

**Why plan:** Touches CLI registration, core modules, tests, and docs — plan prevents rework.

## Comparison

| Task size | Mode | Outcome |
|-----------|------|---------|
| One-line log fix | Direct | Fast, no plan overhead |
| New validate command | Plan | File list agreed before edits |
