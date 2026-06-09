---
name: scaffold-template
description: Scaffold a new CLAUDE.md template under templates/ using team conventions. Use when adding a stack-specific template.
context: fork
allowed-tools: Read, Write, Edit, Glob, Grep
---

# Scaffold template skill

Run this skill when adding a new template to `templates/{category}/{name}.md`.

## Workflow

1. Read `templates/javascript/nextjs-typescript.md` as the reference shape (YAML frontmatter + sections).
2. Create the new template with `name`, `displayName`, `description`, `category`, `tags`, `variables`, and `detects` fields.
3. Include Commands, Architecture, and Conventions sections with `{{variable}}` placeholders.
4. Register detection priority consistent with sibling templates in the same category.
5. Summarize what was created and which `dotclaudemd init --stack` flag selects it.

Keep output concise — this skill runs in an isolated fork so long scaffold drafts do not clutter the main session.
