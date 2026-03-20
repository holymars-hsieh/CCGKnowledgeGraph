# CCGKnowledgeGraph — Project Context

## Dispatcher

Before responding to any task in this project, read `.agent/skills/Ego/SKILL.md`.

## Project Purpose

CCGKnowledgeGraph (CCG-KG) is a living knowledge graph that formalizes cross-domain theories into a structured, layered ontology. Its goal is to surface deep structural isomorphisms between domains (neuroscience, thermodynamics, computation, sociology, etc.) and compress them into reusable knowledge nodes.

## Knowledge Graph Structure

```
docs/
├── L0_AXIOM/        # Universal truths — domain-invariant axioms
├── L1_FRAMEWORK/    # Protocols & systems — operational frameworks
├── L2_MODEL/        # Domain theories — mechanistic models
└── L3_CASE/         # Applied instances — theory grounded in events
```

Nodes use `[[WikiLink]]` syntax. Each node carries frontmatter: `layer`, `tags`, `maturity`.

Templates live in `templates/`. Skills live in `.agent/skills/`. Lexicon entries live in `docs/LX_*/Lexicon/`.

## Skill Roster

| Skill | Trigger |
|---|---|
| **Navigator** | Search, retrieval, Q&A |
| **DeepThinker** | Logic deadlocks, constraint resolution |
| **Dreamer** | Cross-domain synthesis, isomorphism hunting |
| **Rosetta** | Translation, term disambiguation, lexicon management |
| **Wordsmith** | Writing, essay polish, narrative extension |
| **Compressor** | ETL — raw input → structured KG node |
| **Sentinel** | Structural audit — dead links, orphans, layer violations |
| **Scribe** | Git commits, changelogs, diff analysis |

## Critical Rules

- **Compressor & Wordsmith:** Always `Read` the relevant template before generating content. Never guess template structure.
- **Rosetta:** All translated terms must be saved to `docs/LX_*/Lexicon/`. Format: `[中文譯名] (English Term)`.
- **Sentinel:** Reads structure only — no content interpretation, no content suggestions.
- **Navigator → Sentinel escalation:** If a `[[link]]` is broken during pathfinding, dispatch to Sentinel immediately.
- **Formatting:** Never place `**` outside double-byte quotes or brackets. Correct: `「文字」`, `專有名詞(Noun)`.
