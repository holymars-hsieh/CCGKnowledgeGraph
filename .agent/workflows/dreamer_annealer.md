---
description: Orchestrates exploratory simulated annealing to find cross-domain isomorphisms.
---
# Dreamer Annealer Workflow

This workflow orchestrates the **Simulated Annealing** process of the Dreamer skill. It ensures wide, high-entropy exploration across the knowledge graph before cooling down to generate a high-potential hypothesis for DeepThinker.

## Execution Steps

1. **[THE SEEDING]**
   - **Ego** must select an `[[Anchor_Node]]` and specify 1-2 **Distant Domains** (e.g., "Find an isomorphism for [[Action Manifold]] in Sociology").
   - Initialize (or reset) `artifacts/dreamer_memory.md` with Temperature = High.

2. **[PERSONA OVERRIDE]**
   - Read `.agent/skills/Dreamer/SKILL.md`.
   - *Switch persona to DREAMER.* You are now a High-Entropy explorer. Speculation is your primary mandate.

3. **[HIGH-HEAT JUMPING]**
   - Perform at least 3 `[JUMP]` operations using `grep_search` or `list_dir` across different layers (L0-L3).
   - Log each jump with its heuristic mapping in `dreamer_memory.md`. Do NOT worry about precision yet.

4. **[SEMANTIC MUTATION]**
   - For the most "vibrant" jump, perform 2 `[MUTATE]` cycles to refine the structural resonance. 
   - Try to find the "Hidden Manifold" that connects the two seemingly unrelated domains.

5. **[ANNEALING & COOL-DOWN]**
   - Reduce Temperature to Low.
   - Evaluate all generated hypotheses. Select the ONE with the highest structural potential (even if it's weird).
   - Format this as a `[Ready for DeepThinker]` entry.

6. **[BACKLOG PERSISTENCE]**
   - Read the existing `.agent/skills/Dreamer/research_backlog.md`.
   - Append the new hypothesis and prune redundant or lower-quality legacy entries.

7. **[RESTORE EGO & SYNTHESIZE]**
   - **Restore EGO persona.** 
   - Analyze the annealing results. Based on the "High-Potential Hypothesis" and current system state, Ego has the autonomous authority to:
     - Directly invite user feedback.
     - Proactively propose a dispatch to **DeepThinker** for verification.
     - Or determine if further exploration/documentation is needed first.
   - Present the strategic finding and articulate your next proposed action.
