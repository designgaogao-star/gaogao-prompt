# GaoGao Prompt

GaoGao Prompt is a Codex skill for writing, refining, and diagnosing GPT Image / GPT Imagine prompts. It acts as a prompt director: it routes each visual brief into the right workflow, protects reference-image truth, separates visible text from product labels, and returns copy-ready prompts with settings and iteration knobs.

高高 Prompt 是一个 Codex skill，用来撰写、优化和诊断 GPT Image / GPT Imagine 生图提示词。它不是简单堆砌形容词，而是先判断任务类型、保真风险、文字风险和系列一致性，再输出可直接复制执行的提示词。

## What It Helps With

- Single image prompts for product photos, posters, key art, character concepts, and ecommerce visuals.
- Prompt rescue: diagnose weak prompts and rewrite the smallest useful next version.
- Image edits with explicit locked attributes and allowed changes.
- Multi-reference workflows with role mapping and priority order.
- Structured layouts for ecommerce boards, UI mockups, infographics, and storyboards.
- Series bibles for consistent product campaigns or recurring visual systems.
- Exact-text handling, including Chinese poster text and product-label preservation.

## 它适合做什么

- 产品图、电商图、海报、角色图、场景图等单张提示词。
- 失败提示词修复：先判断失败原因，再改最关键的一版。
- 参考图编辑：锁定产品、人物、标签、构图或风格边界。
- 多参考图：为每张图分配身份、风格、构图、光影等角色。
- 结构化版式：电商卖点图、UI、信息图、分镜和对比面板。
- 系列图：建立统一镜头、光线、材质、色温和保真规则。

## Install

Copy the skill folder into your Codex skills directory:

```powershell
Copy-Item -Recurse -Force .\gaogao-prompt "$env:USERPROFILE\.codex\skills\gaogao-prompt"
```

Restart Codex or start a new thread so the skill registry can refresh.

## Usage

Invoke the skill by name in Codex:

```text
$gaogao-prompt 帮我把这个护肤品场景想法改成高级电商图提示词
```

Example request:

```text
Use $gaogao-prompt to create three visual directions for a premium skincare poster.
The product bottle must stay recognizable, no fake efficacy claims, vertical 1024x1536.
```

## Output Modes

- `Final Prompt`: one copy-ready prompt with settings and QA notes.
- `Visual Direction Set`: three distinct creative directions.
- `Prompt Rescue`: diagnosis plus a rewritten prompt.
- `Image Edit`: preservation-first edit prompt.
- `Multi-Reference`: indexed reference map and priority order.
- `Structured Layout`: JSON-shaped prompt for controlled panels.
- `Series Bible`: shared invariants and per-shot prompts.
- `Generated Image Review`: image read, likely failure cause, and next edit.

## Guardrails

- Product truth beats style.
- Supplied text beats decorative layout.
- Product label text is handled separately from poster overlay text.
- Dense or legal-critical typography should fall back to post-production.
- Product and ecommerce prompts must not invent claims, ingredient tables, registration numbers, medical effects, fake labels, or unsupplied logos.

## Validation

The release package is validated with Codex's skill validator. On Windows, run validation in UTF-8 mode because `SKILL.md` intentionally includes Chinese trigger terms:

```powershell
python -X utf8 "$env:USERPROFILE\.codex\skills\.system\skill-creator\scripts\quick_validate.py" .\gaogao-prompt
```

Expected result:

```text
Skill is valid!
```

## Release

Current GitHub release: `v1.0.0`.

The skill payload intentionally contains only the Codex skill files:

- `gaogao-prompt/SKILL.md`
- `gaogao-prompt/agents/openai.yaml`
- `gaogao-prompt/references/*.md`

Release-facing docs such as this README and the changelog stay at the repository root or under `dist/`.
