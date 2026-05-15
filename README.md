# AI Agent Skills

A collection of modular AI agent skills organized by category, designed to support various workflows from writing to development.

These skills are built on the **Open Agent Skills Ecosystem** format, making them universally compatible with any modern AI agent (Claude Code, Gemini CLI, Cursor, Windsurf, Copilot, etc.).

## Repository Structure

Skills are organized into categories:
- **`writing/`**: A complete human writing pipeline (research, drafting, editing, SEO, promotion).

## The Writing Pipeline (`writing/`)

This category contains specialized skills for the writing workflow:

1.  **`researcher`**: Gathers and synthesizes source material.
2.  **`outliner`**: Structures topics, thesis, and headings.
3.  **`drafter`**: Expands outlines into full drafts matching a desired tone.
4.  **`prose-perfectionist`**: Refines copy for grammar, clarity, tone, and flow.
5.  **`humanizer`**: Adjusts the writing to sound more natural, organic, and less "AI-generated".
6.  **`seo-optimizer`**: Suggests keywords, meta descriptions, and formatting for search engines.
7.  **`social-promoter`**: Generates promotional snippets and social media copy.
8.  **`writing-director`**: Orchestrates the entire end-to-end workflow automatically.

## Universal Installation (Any AI Agent)

### 1. Via Open Agent Skills Package Manager
You can use the `skills` CLI to install these directly into your agent's environment:

```bash
# Install the writing category from this repository
npx skills add primidi/skills/writing
```

## How to Use as a Single Workflow

To run the entire writing pipeline at once, use the **`writing-director`** skill.

**Example Prompt:**
> "Use the **writing-director** skill to create a full article about [Topic]. Run the entire pipeline from research to social promotion automatically."

The Director will then coordinate the internal transition between all other skills sequentially.

### 2. Manual Context Injection (Cursor, Windsurf, Copilot)
Since each skill is a self-contained markdown file (`SKILL.md`), you can easily use them in IDE-based agents:
- **Cursor / Windsurf**: Reference the file path (e.g., `@writing/researcher/SKILL.md`).
- **ChatGPT / GitHub Copilot**: Upload or paste the `SKILL.md` file as a system prompt instruction.

### 3. Direct Gemini CLI Installation
You can install these skills directly into the Gemini CLI from the remote GitHub repository:

```bash
# Install specific skills directly from GitHub (Remote)
gemini skills install https://github.com/primidi/skills.git --path writing/writing-director --scope workspace
gemini skills install https://github.com/primidi/skills.git --path writing/researcher --scope workspace

# Reload your skills in the interactive session
/skills reload
```

## Development

To modify these skills:
1. Edit the `SKILL.md` files in each skill's respective category directory.
2. If you are using Gemini CLI, repackage them using the Gemini CLI skill creator tools.
3. If you are using the open agent ecosystem, simply commit and push your changes to GitHub. Your agent will pull the latest version the next time you run `npx skills update`.
