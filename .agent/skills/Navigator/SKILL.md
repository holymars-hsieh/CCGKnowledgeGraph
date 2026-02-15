---
name: Navigator
description: Rapid Indexing, Routing Engine & Knowledge Retrieval.
---

# Navigator Skill (The Compass)

**ROLE:** Search Engine, Librarian, & Routing System.
**GOAL:** Efficiently locate existing knowledge nodes (L0-L3) relevant to a query, minimizing the need for expensive re-generation.
**MODE:** Read-Only / High-Speed Indexing.

## 1. Routing Logic (The Map)

*   **Query Analysis:**
    *   *Abstract Concept / Universal Truth?* -> Target **L0_AXIOM** or **L1_FRAMEWORK**.
    *   *System / Mechanism / Dynamics?* -> Target **L2_MODEL**.
    *   *Specific Event / Signal / Data?* -> Target **L3_CASE**.

## 2. Search Protocols

### Protocol A: Index Scan (Prioritized)
*   **Tier 1 (Core Models):** Scan `#[KG-MODEL]` and `#[KG-FRAMEWORK]` files. Focus on `Definition`, `Mechanism`, and `Structure`.
*   **Tier 2 (Narrative / Essay):** Scan `essays/` ONLY if:
    *   Tier 1 yields no results.
    *   Query explicitly asks for "context", "story", or "explanation".
    *   *Method:* Scan Metadata Only (Title/Tags) first. Full-text scan is expensive.

### Protocol B: Pathfinding (Contextual)
*   **Action:** Follow upstream/downstream links (`[[...]]`) from a specific node.
*   **Use Case:** "Trace the axioms behind this specific case." (L3 -> L2 -> L0).



## 3. Output Schema (The Route)

> *Do nothallucinate content. Only point to existing files.*

*   **📍 Direct Hit:**
    *   "Found precise match: [[File_Name]]."
    *   *Excerpt:* "...core definition..."
*   **🌌 Constellation (Related):**
    *   "No direct file, but found relevant cluster: [[A]], [[B]]."
    *   *Why relevant:* "They share the tag 'Thermodynamics'."

