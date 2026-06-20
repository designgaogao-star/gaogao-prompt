# Model And Settings Reference

Use this when choosing model/tool settings for GPT Image or OpenAI-compatible image generation. Treat **GPT Imagine** as a host/UI or user-facing tool name unless the user supplies its exact API contract; do not assume GPT Imagine has the same parameters as the OpenAI API. If exact API behavior matters, verify current official docs before implementation. This reference was checked against OpenAI image generation docs on 2026-06-20.

Sources:

- OpenAI Image generation guide: https://platform.openai.com/docs/guides/image-generation
- OpenAI Images API reference: https://platform.openai.com/docs/api-reference/images/create

## Contents

- GPT Imagine Alias Policy
- API Mode
- GPT Image 2 Notes
- Quality
- Size
- Variants
- Format
- Background
- Model Limitations To Mention When Relevant
- Settings Block Pattern

## GPT Imagine Alias Policy

- If the user says GPT Imagine but gives no API details, write a strong image prompt and mark settings as `tool default` or `auto`.
- If the user says GPT Image or `gpt-image-2`, use the GPT Image settings below.
- If a host tool exposes its own sizes, quality values, or edit modes, follow that host contract over this reference.

## API Mode

Use **Image API** when:

- The task is one prompt -> one or more images.
- You want to choose the GPT Image model directly.
- You are doing a direct generation or edit call.

Use **Responses API image generation tool** when:

- The work is conversational or multi-turn.
- The model needs to decide whether to generate or edit in context.
- You want to provide image inputs as files inside a larger conversation.
- You need `action: "generate"` or `action: "edit"` behavior in tool mode.

## GPT Image 2 Notes

- `gpt-image-2` supports generation and edits.
- It can accept multiple input images for reference/edit workflows.
- Omit `input_fidelity` for `gpt-image-2`; image inputs are processed at high fidelity automatically.
- Transparent backgrounds are not currently supported for `gpt-image-2`; use opaque or automatic backgrounds.
- Masked edits are prompt-guided. Masks help but may not be followed with pixel-perfect precision.

## Quality

| Quality | Use for |
|---|---|
| `low` | Fast drafts, thumbnails, quick exploration, many variants |
| `medium` | Normal style tests and early client-facing options |
| `high` | Final posters, exact Chinese text, UI/infographic layouts, close-up portraits, product label legibility, ecommerce deliverables |
| `auto` | Unknown target or tool-managed defaults |

Start low when exploring composition. Move to high only when the prompt, layout, and text are stable.

## Size

Common GPT Image 2 sizes:

| Size | Use |
|---|---|
| `1024x1024` | Square ecommerce main image, avatar, concept |
| `1536x1024` | Landscape banner, website hero, cinematic horizontal |
| `1024x1536` | Poster, social vertical, ecommerce detail visual |
| `2048x2048` | 2K square final when detail matters |
| `2048x1152` | 2K landscape |
| `3840x2160` | 4K landscape, experimental/heavier |
| `2160x3840` | 4K portrait, experimental/heavier |
| `auto` | Unknown channel or API-managed selection |

Constraints for GPT Image 2 custom sizes:

- Maximum edge length must be less than or equal to `3840px`.
- Both edges must be multiples of `16px`.
- Long edge to short edge ratio must not exceed `3:1`.
- Total pixels must be from `655,360` through `8,294,400`.
- Outputs above `2560x1440` total pixel scale are experimental and may be slower or less stable.

## Variants

- Use `n: 1` for controlled edits, exact text, and high-cost final attempts.
- Use `n: 2-4` for visual directions and prompt exploration.
- Use `n: 4` when exact text is short but likely to need selection.
- For series, generate the style anchor first, then create each series prompt separately.

## Format

- `png` is a strong default for quality and transparency-adjacent workflows, even when the model returns opaque output.
- `jpeg` can be faster and smaller for photographic drafts.
- `webp` can be useful for web delivery.
- Use compression only for final delivery constraints, not prompt evaluation.

## Background

- Use opaque/auto by default for `gpt-image-2`.
- For cutouts, generate a clean white or solid background and remove the background downstream if transparency is required.

## Model Limitations To Mention When Relevant

- Exact text can still fail, especially dense typography, long copy, or precise layout.
- Recurring characters or brand elements can drift across generations.
- Structured layouts can be imprecise.
- Complex prompts can take longer and may need smaller iterative steps.
- User-correctable errors should change the prompt or inputs, not just retry blindly.

## Settings Block Pattern

```markdown
Settings:
- mode: [text-to-image / image edit / multi-reference edit]
- model/tool: gpt-image-2 or target image tool
- quality: [low / medium / high / auto]
- size: [recommended size]
- variants: [n]
- format: [png / jpeg / webp / tool default]
```
