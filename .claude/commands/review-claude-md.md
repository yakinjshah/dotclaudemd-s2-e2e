---
description: Run the dotclaudemd CLAUDE.md review checklist before merge.
---

Review the project's CLAUDE.md files (root, `src/CLAUDE.md`, and `.claude/rules/*`) against this checklist:

1. Build, test, and lint commands are present and accurate.
2. Modular `@import` paths resolve to real files under `claude/`.
3. Path-specific rules use YAML frontmatter with `globs` patterns.
4. No persona fluff ("act as senior engineer") — keep instructions actionable.
5. File paths referenced in CLAUDE.md exist in the repo.

Output a numbered list of issues with file path, severity (low/med/high), and a one-line fix.
