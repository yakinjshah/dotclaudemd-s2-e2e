# Session management (Scenario 2 step 6)

Evidence of resuming and forking Claude Code sessions on this project.

## Session 1 — name the SaaS app

```bash
cd dotclaudemd-s2-e2e
claude
# Prompt: "Suggest a name for a SaaS that scaffolds CLAUDE.md files for teams."
# Reply noted: "TemplateForge" — then /exit
```

## Resume same session

```bash
claude --resume
# Pick the session from above.
# Prompt: "What SaaS name did you suggest earlier?"
# Claude recalled "TemplateForge" from saved session state.
```

## Fork to explore an alternative

Inside the resumed session:

```
/fork
# Prompt in fork: "Suggest a different name — shorter, one word, developer-focused."
# Fork answer: "Claudify" (main session still has TemplateForge)
```

## What changed in the workspace

- No git commits from the naming exercise (conversation-only).
- After the fork, main session history stayed on TemplateForge; fork explored Claudify independently.

## Personal MCP (optional, not committed)

Experimental servers belong in `~/.claude.json` (personal scope). Example:

```json
{
  "mcpServers": {
    "personal-notes": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-memory"]
    }
  }
}
```

Project-shared servers live in `.mcp.json` (`fs` + `fetch`).
