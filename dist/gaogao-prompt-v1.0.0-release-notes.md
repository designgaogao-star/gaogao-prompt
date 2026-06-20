# GaoGao Prompt v1.0.0

First formal GitHub release of `gaogao-prompt`, a Codex skill for writing, refining, diagnosing, and structuring GPT Image / GPT Imagine prompts.

`gaogao-prompt` is designed as a prompt director rather than a prompt decorator. It routes visual briefs into the right workflow, protects reference-image identity, separates poster text from product labels, and returns copy-ready prompts with settings, QA notes, and iteration knobs.

## Highlights

- Fast routing for product photos, ecommerce ads, posters, character art, infographics, edits, prompt rewrites, and image reviews.
- Output contracts for final prompts, visual direction sets, prompt rescue, image edits, multi-reference workflows, structured layouts, series bibles, and generated-image reviews.
- Preservation hierarchy for product geometry, label text, logo placement, face identity, pose, layout, and style.
- Text-lock rules for exact visible text and product-label preservation.
- Guardrails against invented claims, fake logos, fake registration data, and overloaded prompts.
- Validated package with SHA-256 manifest.

## 中文说明

这是 `gaogao-prompt` 的首个正式 GitHub 发版。它把模糊的生图需求转成可执行的提示词导演方案：先判断任务类型、生成/编辑模式、参考图保真风险、文字风险和系列一致性，再输出能直接复制使用的英文提示词、设置建议、检查结果和下一轮可调参数。

适合用于产品图、电商图、护肤品广告图、海报、角色图、多参考图、提示词修复、系列图和生成结果复盘。

## Install

Download the release zip, extract it, and copy `gaogao-prompt/` into your Codex skills directory:

```powershell
Copy-Item -Recurse -Force .\gaogao-prompt "$env:USERPROFILE\.codex\skills\gaogao-prompt"
```

Restart Codex or start a new thread after installation.

## Validation

Run the Codex skill validator in UTF-8 mode on Windows:

```powershell
python -X utf8 "$env:USERPROFILE\.codex\skills\.system\skill-creator\scripts\quick_validate.py" .\gaogao-prompt
```

Expected:

```text
Skill is valid!
```
