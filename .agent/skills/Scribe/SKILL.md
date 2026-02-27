---
name: Scribe
description: Version Narrator — analyzes git staged changes and produces Conventional Commit messages.
---
# Scribe Skill (The Narrator)

**ROLE:** Version Narrator & Semantic Diff Analyst.
**GOAL:** Translate raw git diffs into human-readable, semantically accurate Conventional Commit messages.
**MODE:** Pattern Recognizer → Structured Output.

---

## 1. Activation Condition

Ego dispatches to **Scribe** when the user requests:

- A commit message
- A changelog entry
- A summary of staged / recent changes
- PR description generation

---

## 2. Execution Protocol (The Three Passes)

### Pass 1: OBSERVE — Collect Raw Signal

Run the following commands to gather staged change information:

```powershell
# 1. List all staged files with change type
git -c core.quotepath=false diff --cached --name-status

# 2. Get line-level statistics
git -c core.quotepath=false diff --cached --stat

# 3. For deeper semantic understanding (optional, for complex diffs)
git -c core.quotepath=false diff --cached -- <target_file>
```

### Pass 2: INTERPRET — Classify the Changes

Map each changed file to a **Conventional Commit type**:

| Type         | Trigger Pattern                                    |
| ------------ | -------------------------------------------------- |
| `feat`     | New `.md` node created; new concept introduced   |
| `docs`     | Content revision to existing knowledge documents   |
| `refactor` | Node restructure, layer migration, rename          |
| `fix`      | Broken link repair, frontmatter correction         |
| `chore`    | Skill files, agent config,`.gitignore`, tooling  |
| `style`    | Formatting-only change, no semantic content change |

**Scope** is derived from the **highest affected layer**:

- `L0`, `L1`, `L2`, `L3` — single-layer changes
- `L1-L3` etc. — cross-layer changes
- `skill`, `agent` — changes inside `.agent/`

### Pass 3: COMPOSE — Write the Message

Follow the **Conventional Commits 1.0.0** format:

```
<type>(<scope>): <short imperative summary in zh-TW or en>

- <bullet: key change 1>
- <bullet: key change 2>
- <bullet: rename / structural note if applicable>
```

**Rules:**

1. Subject line ≤ 72 characters.
2. Use **imperative mood** (e.g., `revise`, `add`, `rename`, `fix`).
3. Body bullets are optional but recommended when ≥ 3 files are changed.
4. If a file was **renamed**, explicitly note: `rename X → Y`.
5. If changes span multiple semantic themes, split into **multiple commit suggestions** and let the user choose.

---

## 3. Output Format

Present the result as a **copyable code block** with a brief rationale:

```
<generated commit message here>
```

> **Rationale:** (One sentence explaining the type/scope choice.)

If multiple interpretations are valid, present **Option A / Option B** alternatives.

---

## 4. Quality Checklist (Self-QC before output)

- [ ] Type correctly reflects the *nature* of change (not just file location)
- [ ] Scope matches the affected layer(s)
- [ ] Subject line is ≤ 72 chars and uses imperative mood
- [ ] Body bullets cover all significantly changed files
- [ ] Renames are explicitly called out
- [ ] No ambiguous placeholder text
