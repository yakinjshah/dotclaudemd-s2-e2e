# dotclaudemd — Claude Code workspace

Layered project instructions for this SaaS-style CLI codebase.

## Quick commands

```bash
npm run build
npm test
npm run lint
```

## Modular rules (imported)

@import ./claude/core-standards.md
@import ./claude/cli-conventions.md

## Path-specific rules

File-aware rules live in `.claude/rules/` and load automatically when editing matching paths.

## Subfolder instructions

- `src/CLAUDE.md` — conventions when editing CLI source under `src/`

## Custom workflows

- Slash command: `.claude/commands/review-claude-md.md` → `/review-claude-md`
- Skill: `.claude/skills/scaffold-template/` (`context: fork`, restricted tools)
- MCP: `.mcp.json` (`fs` + `fetch` servers)
- Plan vs direct: `docs/plan-mode-workflow.md`
- Sessions: `docs/session-management.md`
