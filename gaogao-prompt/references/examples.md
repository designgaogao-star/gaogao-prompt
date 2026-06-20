# Annotated Examples

Use these when the task is hard, the prompt needs rescue, or a future agent needs a gold standard for output structure. Do not copy the examples blindly; adapt the structure.

## Contents

- Example 1: Chinese Skincare Poster Rescue
- Example 2: Product Reference Edit
- Example 3: Game Poster Direction Set
- Example 4: Six-Image Ecommerce Series

## Example 1: Chinese Skincare Poster Rescue

User brief:

```text
帮我把这个提示词优化得高级一点：蓝色护肤品海报，水润，文字是“48小时长效保湿”，产品在中间，背景有水。
```

Diagnosis:

- Needs exact Chinese text.
- Ecommerce skincare prompt must not invent claims beyond supplied text.
- Needs product label policy.
- Needs high quality and vertical size.

Output pattern:

````markdown
Main issues:
- "高级" is not translated into camera, lighting, and material choices.
- Exact Chinese text needs a text lock and high quality.
- Product label text and poster overlay text need separate policies.

Text lock:
- Poster/overlay text: "48小时长效保湿"
- Product label text: preserve from reference if a product image is provided; otherwise use no fake label text.

Rewritten prompt:
```text
Create a vertical premium skincare advertising poster with a single blue moisturizing serum bottle as the hero, centered on a translucent glass plinth surrounded by controlled water refraction and fine dewy droplets.

Scene/Background: clean pale blue to soft white gradient, subtle water ripple caustics, minimal negative space around the product.
Subject: one skincare bottle, front-facing, label area clean and legible. If a reference product image is provided, preserve its exact bottle shape, cap, label text, logo position, color, proportions, and material finish.
Key Details: soft diffused studio key light, gentle cyan rim light, realistic glass thickness, crisp product edges, restrained premium beauty composition.
Typography: include ONLY this poster overlay text, EXACT, verbatim, no extra characters: "48小时长效保湿". Clean sans-serif Chinese typography, high contrast, placed once in the upper title-safe area.
Constraints: no extra claims, no ingredient table, no registration number, no fake logos, no watermark, no extra text, no people, no clutter, no overdone CGI shine.
```

Settings:
- mode: text-to-image or image edit if product reference exists
- quality: high
- size: 1024x1536
- variants: 4

Fallback:
- If exact text fails or legal precision matters, generate without text and add typography in post.
````

## Example 2: Product Reference Edit

User brief:

```text
把这张瓶子图变成高级护肤品广告场景。
```

Output pattern:

````markdown
Reference audit:
- Locked attributes: bottle shape, cap, label text, logo position, color, material finish, front-facing perspective, product proportions.
- Allowed changes: background, surface, props, contact shadow, reflections, atmosphere.
- Risk: "高级" is too broad, so the prompt chooses quiet luxury spa editorial.

Edit prompt:
```text
Change ONLY the environment around the product in Image 1.
Keep the product exactly the same: bottle shape, cap, label text, logo position, color, proportions, material finish, camera perspective, and visible front face.

Restage the product as a premium quiet-luxury skincare advertisement on a warm travertine stone surface beside a soft frosted window. Add a folded ivory linen towel, a single dewy white camellia flower, and subtle water droplets near the base. Use natural morning side light, soft contact shadows, realistic glass reflections, and clean negative space.

Do not alter, redraw, relabel, resize, recolor, or rebrand the product. No extra text, no fake logos, no hands, no face, no clutter, no watermark, no over-polished CGI shine.
```

Settings:
- mode: image edit
- quality: high
- size: preserve source aspect or 1024x1536
````

## Example 3: Game Poster Direction Set

User brief:

```text
给我的末日科幻游戏做三版电影感海报提示词。
```

Output expectations:

- Three directions, not three minor variants.
- Each direction includes poster composition and title-safe area.
- No fake logo unless supplied.

Direction axes:

| Direction | Composition | Palette | Narrative |
|---|---|---|---|
| Last Signal | lone figure silhouette | cobalt/cyan black | mystery and survival |
| Ash Giant | small human vs huge machine | toxic orange/charcoal | scale and danger |
| White Room Ruin | sterile lab collapsing | cool white/red warning | clinical horror |

## Example 4: Six-Image Ecommerce Series

User brief:

```text
给这款补水精华做 6 张详情页系列图提示词，风格统一。
```

Output expectations:

- Style anchor first.
- Shared invariants repeated.
- Per-image prompts change one variable.
- No invented efficacy data.

Common shot plan:

| # | Role | Controlled variable |
|---|---|---|
| 1 | Hero packshot | product stance |
| 2 | Texture macro | gel/serum texture |
| 3 | Hydration mood | water refraction |
| 4 | Usage scene | hand or bathroom counter if allowed |
| 5 | Supplied benefit visual | one supplied benefit only |
| 6 | Closing brand image | packshot and supplied slogan |
