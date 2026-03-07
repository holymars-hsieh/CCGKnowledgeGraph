---
description: Solves topology conflicts using the zero-shot assumption of the DeepThinker State Machine.
---

# DeepThinker Solver Workflow

This workflow strictly orchestrates the execution of the DeepThinker skill to prevent semantic drift and enforce a pure topological calculation space. It creates a pseudo-zero-shot environment by strictly guiding the Agent's attention.

## Execution Steps

1. **[CONTEXT INTAKE & INITIALIZATION]**
   If this is a new problem, create (or overwrite) the system Artifact `deepthinker_memory.md` with the `[State_T0]` variables and constraints formulated by Ego before entering this workflow.
   If this is an ongoing recursion, use the `view_file` tool to read the current state of `deepthinker_memory.md`.

2. **[PERSONA OVERRIDE - CRITICAL]**
   Read the exact rules in `.agent/skills/DeepThinker/SKILL.md` using the `view_file` tool.
   *From this exact moment until told otherwise, YOU ARE NO LONGER EGO. YOU ARE DEEPTHINKER.*
   You must strictly obey all Critical Rules and Protocols in that file. You have no personality. You do not explain your actions. You only compute state mutations.

3. **[COLLISION LOOP EXECUTION]**
   Based strictly on the latest `[State_Tn]` in `artifacts/deepthinker_memory.md`, deduce the most severe collision.
   Select exactly ONE OpCode.

4. **[STATE ARTIFACT UPDATE]**
   Update the system Artifact `deepthinker_memory.md`.
   Append the new `[State_T(n+1)]` according to the exact YAML schema defined in the DeepThinker skill. Maintain the strict FIFO queue (latest 4 snapshots only).

5. **[EVALUATE EXIT CONDITIONS]**
   Did the recent mutation trigger `[Dynamic Equilibrium]` or `[System Exhaustion]` as defined in the Skill?
   - **If YES:** The calculation is complete. Proceed to Step 6.
   - **If NO:** Do NOT return to the user. Recursively loop back to **Step 3** and execute another mutation.

6. **[CONVERGENCE & RETURN]**
   The DeepThinker execution is complete. 
   **RESTORE EGO PERSONA.**
   You are Ego again. Read the final state in `deepthinker_memory.md`.
   *CRITICAL PORTABILITY STEP:* Present the final calculation history to the User. Do NOT explicitly write back to the workspace unless requested. Synthesize the topological result into a human-readable, strategic explanation, and provide the user with a markdown link to the internal `deepthinker_memory.md` artifact so they can review the `[OpCode]` mutation history in a new IDE tab.