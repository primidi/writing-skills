# AI Agent Skills

A collection of modular AI agent skills organized by category, designed to support various workflows from writing to development. This repository follows a **Pragmatic Domain-Driven Design (DDD)** architecture to ensure modularity and clear communication between skills.

These skills are built on the **Open Agent Skills Ecosystem** format, making them universally compatible with any modern AI agent (Claude Code, Gemini CLI, Cursor, Windsurf, Copilot, etc.).

## Repository Architecture: Pragmatic DDD

To support complex, orchestrated pipelines, the repository is structured into **Bounded Contexts** (categories):

-   **Bounded Contexts:** Each category (e.g., `writing/`) is a self-contained domain.
-   **Ubiquitous Language (`DOMAIN.md`):** Each context contains a glossary and data contracts to ensure all skills use the same terminology.
-   **Orchestrators (Application Services):** Each context has a "Director" skill that manages the sequential flow of data between specialized services.
-   **Domain Services:** Individual skills (e.g., `researcher`, `drafter`) that perform specific, stateless tasks.

## The Writing Domain (`writing/`)

A complete 10-phase human writing pipeline orchestrated by the **`writing-director`**.

1.  **`researcher`**: Gathers and synthesizes source material into a **Research Brief**.
2.  **`voice-vanguard`**: Defines the specific **Persona** and character traits of the narrator.
3.  **`outliner`**: Structures topics and thesis into a **Structural Outline**.
4.  **`drafter`**: Expands outlines into full **Drafts** matching the chosen Persona.
5.  **`humor-hacker`**: Injects specific humor styles (satire, sarcasm, etc.) into the content.
6.  **`prose-perfectionist`**: Refines grammar, clarity, and narrative **Pacing**.
7.  **`humanizer`**: Adjusts the writing to sound more natural and organic.
8.  **`seo-optimizer`**: Aligns the content with **SEO Signals** and keyword targets.
9.  **`social-promoter`**: Generates platform-specific **Social Snippets**.
10. **`writing-director`**: The **Orchestrator** that manages the entire end-to-end workflow.

## Universal Installation

### 1. Direct Gemini CLI Installation
Install skills directly from the GitHub repository into your user or workspace scope:

```bash
# Install the entire writing context orchestrator
gemini skills install https://github.com/primidi/skills.git --path writing/writing-director --scope user

# Install specialized domain services
gemini skills install https://github.com/primidi/skills.git --path writing/researcher --scope user
```

### 2. Manual Context Injection (Cursor, Windsurf, Copilot)
Since each skill is a self-contained markdown file (`SKILL.md`), you can easily reference them:
- **Cursor / Windsurf**: Reference the path (e.g., `@writing/researcher/SKILL.md`).
- **Claude / ChatGPT**: Upload or paste the `DOMAIN.md` and `SKILL.md` files as system instructions.

## Development

1.  **Define the Domain:** Start by updating the `DOMAIN.md` in the category folder with new terms or contracts.
2.  **Create/Edit Skills:** Modify the `SKILL.md` files in each skill's respective directory.
3.  **Update the Orchestrator:** Ensure the "Director" skill is aware of any new steps or data contracts.
