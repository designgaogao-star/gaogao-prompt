# Prompt Recipes

Use this as the routing layer after `SKILL.md` classifies the brief. A recipe is not a template; it is a production workflow for choosing inputs, priorities, output structure, settings, and repair logic.

## Contents

- Recipe Contract
- Brief Intake
- Mode Selection Matrix
- Recipe 1: Brief Intake And Mode Router
- Recipe 2: Product Hero Studio Image
- Recipe 3: Product Environment Edit
- Recipe 4: Exact Text Poster Or Billboard
- Recipe 5: Visual Direction Set
- Recipe 6: Ecommerce Detail Board / Structured Layout
- Recipe 7: Multi-Reference Product Campaign
- Recipe 8: Character Sheet / Expression Grid
- Recipe 9: Series Bible
- Recipe 10: Prompt Rescue And Repair

## Recipe Contract

Every recipe should answer these fields when they materially affect the output. If a recipe omits `Settings` or `Iteration knobs`, use the standard settings and iteration blocks from `SKILL.md`.

- **Use when:** request signals that trigger the recipe.
- **Mode:** text-to-image, image edit, masked edit, multi-reference edit, structured JSON, prompt rescue, or series.
- **Required inputs:** what must be known before writing.
- **Assumptions:** safe defaults when the user does not specify.
- **Reference priority:** what wins when references conflict.
- **Prompt structure:** how to assemble the final prompt.
- **Preservation clauses:** what must remain unchanged.
- **Negative constraints:** likely failure modes to exclude.
- **Settings:** quality, size, variants, and format.
- **Iteration knobs:** small variables to change next.
- **Self-check:** pass/fail checks before output.

## Brief Intake

Use this compact intake schema internally:

```text
goal:
final use/channel:
subject:
input references:
must preserve:
exact text:
brand/product truth:
style direction:
size/aspect:
series needs:
known risks:
```

Ask one question only when the missing answer changes mode or preservation. Otherwise proceed with explicit assumptions.

Critical missing facts:

- Reference image exists but preservation is unclear.
- Text must appear but exact text is not supplied.
- User asks for a product/person edit but no source image is available.
- User asks for a series but does not say whether the subject or style is constant.
- User asks for an ad with claims that may be invented or regulated.

## Mode Selection Matrix

| Situation | Mode | Notes |
|---|---|---|
| New scene from imagination | text-to-image | Good for posters, illustrations, concepts |
| Product/person must stay accurate | image edit | Preserve identity and geometry explicitly |
| Product + style + layout references | multi-reference edit | Index each image by role |
| Board, UI, infographic, storyboard | structured JSON prompt | Separate layout, text, style, subject |
| Weak prompt needs improvement | prompt rescue | Diagnose issues before rewrite |
| Long exact typography | generate without text + post-production | Use only short exact text in image |
| Consistent multi-image set | series bible | Build anchor and repeat invariants |

## Recipe 1: Brief Intake And Mode Router

Use when the user gives a vague idea or asks for "a prompt".

Output:

- Brief diagnosis
- Assumptions
- Final prompt
- Settings
- Iteration knobs

Prompt construction:

```text
Create [final use] featuring [subject].
Scene/Background: [environment, time, mood]
Subject: [hero subject, action, product/person details]
Key Details: [camera, lighting, composition, material, palette]
Style: [medium/rendering/visual language]
Constraints: [negative constraints and preservation]
```

Self-check:

- One focal subject.
- Concrete visual terms, not only mood words.
- Settings match use.

## Recipe 2: Product Hero Studio Image

Use for ecommerce main images, product ads, catalog hero shots, or premium product photography.

Mode:

- Text-to-image when no real product exists.
- Image edit when a product photo exists.

Required inputs:

- Product type, shape, packaging, brand text if any.
- Whether exact label/logo must be preserved.
- Final channel: square main image, banner, detail page.

Reference priority:

1. Product geometry, color, label, logo, material.
2. Camera angle and visible face.
3. Background and props.
4. Mood/style.

Required clauses:

```text
Preserve the exact product geometry, cap shape, label text, logo position, color, proportions, and material finish. Do not restyle the product.
```

If no source product image:

```text
Use only the supplied brand/product text. Do not invent claims, ingredient tables, certification marks, registration numbers, or fake logos.
```

Settings:

- `quality: medium` for first style tests.
- `quality: high` for final ecommerce deliverables or label legibility.
- `size: 1024x1024` for main image, `1536x1024` for banner, `1024x1536` for vertical detail.

Iteration knobs:

- Background material.
- Rim light color.
- Lens and angle.
- Prop density.

## Recipe 3: Product Environment Edit

Use when the user uploads a product photo and wants a premium/lifestyle/studio scene.

Intake:

- Reference audit: shape, cap, label, logo, color, material, camera angle.
- Allowed changes: background, surface, props, shadows, reflections, atmosphere.
- Locked attributes: product geometry, label text, logo position, perspective, proportions.

Prompt pattern:

```text
Change ONLY the environment around the product in Image 1.
Keep the product exactly the same: bottle shape, cap, label text, logo position, color, proportions, material finish, camera perspective, and visible front face.
Restage the environment as [scene].
Lighting: [lighting]
Surface/background: [materials]
Props: [sparse props]
Do not alter, redraw, relabel, resize, or rebrand the product.
No extra text, watermark, fake logos, hands, or unrelated props.
```

Self-check:

- Allowed changes and locked attributes are separate.
- The prompt does not say "keep everything the same" if the background must change.
- Product truth is repeated in the final prompt.

## Recipe 4: Exact Text Poster Or Billboard

Use for short exact text, Chinese poster text, billboard mockups, sale banners, or brand slogans.

Required inputs:

- Exact visible text.
- Whether product label text also appears.
- Typography style and text zone when known.

Text lock:

```text
Include ONLY this poster overlay text, EXACT, verbatim, no extra characters:
"[line 1]"
"[line 2]"
Preserve any existing product label text from the reference image separately.
```

Typography:

- `clean sans-serif Chinese typography` for ecommerce, UI, modern posters.
- `elegant serif Chinese typography` for premium/luxury/editorial.
- `bold condensed sans-serif` for billboards or game posters.

Settings:

- Always use `quality: high`.
- Recommend 2-4 variants for text-heavy attempts.

Fallback:

- If text is long, legal-critical, price-critical, or brand-critical, generate the image without text and add typography in post.

Self-check:

- Exact text is quoted.
- Product labels are not accidentally forbidden by "Include ONLY".
- No extra text, watermark, or fake logos.

## Recipe 5: Visual Direction Set

Use when the user asks for options, style directions, game key art, campaign concepts, or poster exploration.

Each direction must include:

- Positioning.
- Composition.
- Hero subject.
- Background world.
- Lighting and palette.
- Title/logo safe zone.
- Negative constraints.
- Copy-ready prompt.

Directions must differ on at least three axes:

- Composition: centered hero, diagonal action, split-scale, overhead, silhouette.
- Palette: warm gold, cyan-black, toxic orange, monochrome, pastel, high-key white.
- Lighting: rim light, volumetric backlight, neon, storm flash, soft editorial.
- Medium: photoreal, painterly, 3D render, ink/watercolor, graphic poster.
- Narrative: triumph, mystery, danger, serenity, premium trust.

Poster constraints:

```text
Clear focal hierarchy, strong readable silhouette, title-safe area in [top/bottom/center], no fake logos, no random text, no watermark.
```

## Recipe 6: Ecommerce Detail Board / Structured Layout

Use for tall Chinese ecommerce boards, feature panels, UI mockups, infographics, live-stream mockups, and storyboards.

Mode:

- Structured JSON prompt.

Structure:

```json
{
  "type": "[board/ui/storyboard/infographic]",
  "subject": {},
  "style": {},
  "layout": {},
  "text_policy": {},
  "constraints": [],
  "render_output": {}
}
```

Rules:

- Use only supplied claims, benefits, ingredient names, prices, and legal text.
- Use placeholders only if returning a reusable template. Replace placeholders for final prompts.
- Keep text short and sectioned.
- Use `quality: high` for dense layouts.

Self-check:

- No invented data.
- Sections have clear hierarchy.
- Exact text policy is explicit.

## Recipe 7: Multi-Reference Product Campaign

Use when several input images provide different requirements.

Reference map:

```text
Image 1 = product identity and label
Image 2 = style palette and lighting
Image 3 = layout/composition
Image 4 = material/prop reference
```

Conflict priority:

1. Identity, product geometry, label, face, supplied text.
2. Layout and camera composition.
3. Lighting, palette, material.
4. Mood and decorative props.

Prompt pattern:

```text
Use Image 1 only for product identity: preserve [locked attributes].
Use Image 2 only for visual style: [style traits].
Use Image 3 only for layout: [layout traits].
Do not copy unassigned objects, text, people, logos, or background details from the references.
```

Self-check:

- Every input has a role.
- Unassigned reference details are explicitly excluded.
- Product/person identity wins over style.

## Recipe 8: Character Sheet / Expression Grid

Use for mascots, stickers, character consistency, expression grids, avatars, or recurring illustration systems.

Lock:

- Face shape.
- Proportions.
- Hairstyle.
- Outfit.
- Palette.
- Line/render style.
- Camera distance.
- Pose constraints.

Prompt structure:

```text
Create a [number]-panel character sheet of [character].
Keep the same identity across all panels: [locked attributes].
Panels: [list].
Style: [medium], [line/render traits], [palette].
Constraints: no outfit drift, no face drift, no extra characters, no text unless supplied.
```

Settings:

- Use `quality: high` for final character sheets.
- Use simpler grids when identity drift appears.

## Recipe 9: Series Bible

Use for product campaigns, 6-image ecommerce sets, social carousel prompts, or consistent style packs.

Deliverable:

1. Style anchor prompt.
2. Shared invariants.
3. Shot plan table.
4. Per-image prompts.
5. Claim/text safety note.

Common 6-shot ecommerce plan:

| # | Role | Controlled variable |
|---|---|---|
| 1 | Hero image | product stance/background |
| 2 | Texture macro | texture/material close-up |
| 3 | Ingredient or mood visual | supplied ingredient or abstract benefit |
| 4 | Usage scene | hand/body/lifestyle if allowed |
| 5 | Detail-page benefit visual | supplied benefit only |
| 6 | Closing brand image | packshot or slogan |

Rules:

- Each image repeats invariants.
- Change only one major variable per prompt.
- Do not invent efficacy data, ingredient tables, registration numbers, or medical claims.

## Recipe 10: Prompt Rescue And Repair

Use when the user brings a weak prompt, failed image, or "make it better".

Diagnose:

- Wrong mode.
- Vague style.
- Competing art styles.
- Missing camera/light/material.
- Missing preservation.
- Unsupported exact text.
- Invented claims.
- Overloaded scene.
- Placeholder residue.

Repair moves:

- Simplify to one visual thesis.
- Convert to image edit.
- Convert to multi-reference.
- Convert to JSON layout.
- Split into anchor plus variants.
- Move text to post-production.
- Add preservation hierarchy.
- Add negative constraints for the observed failure.

Output:

- Main issues.
- Rewritten prompt.
- Settings.
- Why it works better.
- Fallback.
