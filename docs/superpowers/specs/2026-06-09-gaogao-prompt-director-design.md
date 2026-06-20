# GaoGao Prompt Director Design

## Goal

Upgrade `gaogao-prompt` from a prompt template guide into a best-in-class prompt director for GPT Image / GPT Imagine workflows.

## Project Understanding

The current skill already has a strong compact `SKILL.md`, a template library, and craft rules. Its main weakness is that it depends on the model choosing the right workflow from scattered guidance. The next version should explicitly route a user brief into a recipe, choose generation or edit mode, preserve references correctly, recommend model settings, and output copy-ready prompts with iteration knobs.

## Recommended Approach

Use a progressive disclosure architecture:

- Keep `SKILL.md` as the fast router and output contract.
- Add `references/prompt-recipes.md` for workflow recipes and failure-mode handling.
- Add `references/model-settings.md` for current GPT Image parameters and cost/quality guidance.
- Add `references/style-vocabulary.md` for high-signal visual language.
- Tighten `craft-rules.md` and `templates.md` so they support the recipes without bloating the main skill.

## Output Contracts

The skill should support these high-quality outputs:

- Single final prompt with settings and iteration knobs.
- Three visual directions with meaningful differences.
- Prompt diagnosis and rewrite.
- Image-edit prompt with explicit preservation hierarchy.
- Multi-reference prompt with indexed references and role mapping.
- Series plan for multiple consistent images.
- Exact text prompt for Chinese typography and poster work.

## Constraints

- Do not add scripts unless deterministic automation becomes necessary.
- Do not create README-style documentation inside the skill.
- Keep all detailed knowledge one level under `references/`.
- Validate the skill with `quick_validate.py`.
- Sync the optimized skill into `C:\Users\79974\.codex\skills\gaogao-prompt` after local validation.

## Success Criteria

- `SKILL.md` can route common image-generation requests without reading every reference.
- Recipes cover product, ecommerce, poster, illustration, edit, multi-reference, exact text, and series workflows.
- Model settings match current official OpenAI GPT Image guidance.
- Prompt outputs are copy-ready and include practical settings.
- Office records and installed copy are updated.
