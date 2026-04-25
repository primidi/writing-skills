# Human Writing Workflow AI Agent Skills

A suite of modular AI agent skills designed to support the complete human writing pipeline—from initial research to final social media promotion. 

These skills are built on the **Open Agent Skills Ecosystem** format, making them universally compatible with any modern AI agent (Claude Code, Gemini CLI, Cursor, Windsurf, Copilot, etc.).

## The Granular Pipeline

This repository contains seven specialized skills that can be used sequentially or individually:

1.  **`researcher`**: Gathers and synthesizes source material.
2.  **`outliner`**: Structures topics, thesis, and headings.
3.  **`drafter`**: Expands outlines into full drafts matching a desired tone.
4.  **`editor`**: Refines copy for grammar, clarity, tone, and flow.
5.  **`humanizer`**: Adjusts the writing to sound more natural, organic, and less "AI-generated".
6.  **`seo-optimizer`**: Suggests keywords, meta descriptions, and formatting for search engines.
7.  **`social-promoter`**: Generates promotional snippets and social media copy.

## Universal Installation (Any AI Agent)

### 1. Via Open Agent Skills Package Manager (Claude Code, Gemini CLI)
You can use the `skills` CLI to install these directly into your agent's environment:

```bash
# Install ALL skills from this repository
npx skills add primidi/writing-skills

# Or install a specific skill into your workspace
npx skills add primidi/writing-skills@researcher
npx skills add primidi/writing-skills@editor

# For Claude Code specifically:
# The skills will be added to your .claude/ directory automatically.
```

### 2. Manual Context Injection (Cursor, Windsurf, Copilot)
Since each skill is a self-contained markdown file (`SKILL.md`), you can easily use them in IDE-based agents:
- **Cursor / Windsurf**: Copy the contents of a `SKILL.md` (e.g., `researcher/SKILL.md`) into your `.cursorrules` or `.windsurfrules` file, or simply `@` reference the file in chat (`@researcher/SKILL.md`).
- **ChatGPT / GitHub Copilot**: Upload or paste the `SKILL.md` file as a system prompt instruction or reference it in the chat workspace.

### 3. Local Installation (Gemini CLI)
If you have the source files locally, you can install the packaged `.skill` files directly into Gemini CLI:

```bash
# Install from the dist directory
gemini skills install dist/humanizer.skill --scope workspace

# Reload your skills in the interactive session
/skills reload
```

## Development

To modify these skills:
1. Edit the `SKILL.md` files in each skill's respective directory.
2. If you are using Gemini CLI, repackage them using the Gemini CLI skill creator tools.
3. If you are using the open agent ecosystem, simply commit and push your changes to GitHub. Your agent will pull the latest version the next time you run `npx skills update`.
