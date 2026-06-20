# GaoGao Prompt Director Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Upgrade `gaogao-prompt` into a best-in-class prompt director for GPT Image / GPT Imagine prompt writing.

**Architecture:** Keep `SKILL.md` as a compact router and move dense workflow knowledge into focused reference files. Validate locally, then sync the skill into the installed Codex skills directory.

**Tech Stack:** Markdown skill files, Codex skill metadata, GaoGao Office records, `quick_validate.py`.

---

### Task 1: Update Office Task State

**Files:**
- Modify: `Agent Office/task-board.md`
- Modify: `Agent Office/Employees/pm/current-task.md`
- Modify: `Agent Office/communication.md`

- [x] **Step 1: Mark T-001 active**

Record that BOSS approved the high-end optimization and allowed subagents.

- [x] **Step 2: Record current task**

Set the project manager current task to `T-001`.

### Task 2: Create Director References

**Files:**
- Create: `gaogao-prompt/references/prompt-recipes.md`
- Create: `gaogao-prompt/references/model-settings.md`
- Create: `gaogao-prompt/references/style-vocabulary.md`

- [x] **Step 1: Write recipe taxonomy**

Include recipes for brief intake, product hero, product edit, ecommerce series, exact text, cinematic poster, character consistency, multi-reference, infographic/layout, and prompt rescue.

- [x] **Step 2: Write model settings reference**

Include GPT Image 2 size constraints, quality choices, output format notes, background support, `input_fidelity`, and when to choose Image API versus Responses API.

- [x] **Step 3: Write style vocabulary**

Provide compact, high-signal visual language for camera, lighting, composition, material, palette, rendering medium, and negative constraints.

### Task 3: Rewrite Main Skill Router

**Files:**
- Modify: `gaogao-prompt/SKILL.md`

- [x] **Step 1: Add brief classifier**

Classify request type, image mode, reference risk, exact text risk, and output surface.

- [x] **Step 2: Add reference-loading rules**

Load only the relevant reference: recipes for workflow, model settings for parameters, style vocabulary for visual language, templates only when a reusable pattern is useful.

- [x] **Step 3: Add output contracts**

Define output formats for single prompt, three directions, prompt rescue, image edit, multi-reference, and series plan.

### Task 4: Tighten Existing References

**Files:**
- Modify: `gaogao-prompt/references/craft-rules.md`
- Modify: `gaogao-prompt/references/templates.md`

- [x] **Step 1: Update craft rules**

Add preservation hierarchy, prompt density budget, and exact-text fallback guidance.

- [x] **Step 2: Update templates**

Add notes that templates should be adapted through recipes and remove remaining ambiguous claims.

### Task 5: Validate And Sync Install

**Files:**
- Read: `C:\Users\79974\.codex\skills\.system\skill-creator\scripts\quick_validate.py`
- Sync directory: `C:\Users\79974\.codex\skills\gaogao-prompt`

- [x] **Step 1: Run local skill validation**

Run:

```powershell
python -X utf8 'C:\Users\79974\.codex\skills\.system\skill-creator\scripts\quick_validate.py' 'E:\codex\Skill制作\gaogao-prompt'
```

Expected: `Skill is valid!`

- [x] **Step 2: Sync installed copy**

Remove and copy only `C:\Users\79974\.codex\skills\gaogao-prompt` after validation.

- [x] **Step 3: Run installed validation**

Run:

```powershell
python -X utf8 'C:\Users\79974\.codex\skills\.system\skill-creator\scripts\quick_validate.py' 'C:\Users\79974\.codex\skills\gaogao-prompt'
```

Expected: `Skill is valid!`

### Task 6: Update Office Memory

**Files:**
- Modify: `Agent Office/status.md`
- Modify: `Agent Office/task-board.md`
- Modify: `Agent Office/Employees/pm/memory.md`
- Modify: `Agent Office/Employees/pm/current-task.md`

- [x] **Step 1: Mark T-001 done**

Record changed files, validation, and installed sync.

- [x] **Step 2: Record next action**

Set next action to waiting for BOSS's next skill design or optimization request.

## Self-Review

- Spec coverage: Covers routing, recipes, model settings, style vocabulary, validation, install sync, and office memory.
- Placeholder scan: No unresolved `TBD` or `TODO`.
- Scope check: Focused on one skill; future new skills stay out of this implementation.
