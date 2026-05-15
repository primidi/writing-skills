# Writing Domain: Ubiquitous Language & Contracts

This document defines the specialized terminology and data structures (contracts) used within the `writing/` Bounded Context. All skills in this domain must adhere to these definitions to ensure seamless orchestration.

## 1. Ubiquitous Language

| Term | Definition |
| :--- | :--- |
| **Persona** | The specific identity, voice, and character traits of the narrator, as defined by `voice-vanguard`. |
| **Research Brief** | A synthesized collection of source material, facts, and key information produced by the `researcher`. |
| **Structural Outline** | A hierarchical roadmap of the content (headings, subheadings, and thesis statements) produced by the `outliner`. |
| **Beat** | A discrete unit of information or emotional shift within a draft. |
| **Hook** | The opening element designed to capture attention. |
| **Pacing** | The rhythmic flow and speed of the narrative, managed by the `drafter` and refined by `prose-perfectionist`. |
| **SEO Signal** | Metadata and keyword density targets defined by `seo-optimizer`. |
| **Social Snippet** | A repurposed, platform-specific copy (e.g., for Twitter or LinkedIn) produced by `social-promoter`. |

## 2. Data Contracts (Value Objects)

These are the expected formats passed between skills in the `writing-director` pipeline.

### The Research Brief (Output of `researcher`)
*   **Purpose:** To provide the raw material for the outline and draft.
*   **Format:** Markdown with sections for:
    *   `# Objective` (The core question/goal)
    *   `# Key Findings` (Bulleted list of facts/insights)
    *   `# Sources` (List of URLs or citations)

### The Structural Outline (Output of `outliner`)
*   **Purpose:** To provide the logical skeleton for the draft.
*   **Format:** Hierarchical Markdown:
    *   `# Title`
    *   `## Section Heading`
        *   `### Sub-point / Thesis Statement`

### The Draft (Output of `drafter`)
*   **Purpose:** The first prose expansion of the outline.
*   **Format:** Full-prose Markdown following the structure of the outline and adopting the selected `Persona`.

### The Refined Copy (Output of `prose-perfectionist` / `humanizer`)
*   **Purpose:** Polished, professional-grade prose.
*   **Format:** Markdown with corrected grammar, improved flow, and natural transitions.
