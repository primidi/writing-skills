# Repository Rules: AI Agent Skills

## Architecture: Pragmatic DDD

This repository follows a **Pragmatic Domain-Driven Design (DDD)** architecture to ensure modularity, scalability, and clear boundaries between different sets of skills.

### 1. Bounded Contexts (Categories)
- All skills **MUST** be placed within a category subfolder (e.g., `writing/`, `coding/`).
- Each category represents a **Bounded Context**. Skills within a context should be cohesive and use a shared language.
- Avoid tight coupling between skills in different Bounded Contexts.

### 2. Application Services (Orchestrators)
- Each Bounded Context should have at least one **Orchestrator** skill (e.g., `writing-director`).
- The Orchestrator is the entry point for complex workflows. It manages the sequential execution of Domain Services and the flow of data between them.

### 3. Domain Services (Specialized Skills)
- Individual skills within a category are **Domain Services**.
- Each skill should be surgical and focused on a single, well-defined task (e.g., `researcher`, `outliner`).
- Skills should be stateless regarding the overall pipeline; they receive input and produce a specific output (Value Object).

### 4. Ubiquitous Language & Contracts (`DOMAIN.md`)
- Each Bounded Context **MUST** contain a `DOMAIN.md` file.
- This file defines the **Ubiquitous Language** (key terms) and **Data Contracts** (Value Objects) used within that context.
- All skills in the context must adhere to these definitions to ensure seamless interaction.

## Skill Format & Organization
- Each skill must reside in its own subdirectory within a category folder.
- The subdirectory name must be the skill name (e.g., `writing/researcher/`).
- The subdirectory **MUST** contain a `SKILL.md` file following the Open Agent Skills format.

### 3. Documentation
- When adding a new category, update the `README.md` to include the new category in the "Repository Structure" section.
- Add a dedicated section for the new category detailing the skills it contains.

## Installation Consistency
- Ensure that installation instructions in `README.md` and any other documentation use the relative paths (e.g., `gemini skills install ... --path category/skill-name`).
- For Gemini CLI, use the `--scope workspace` flag by default in examples.
