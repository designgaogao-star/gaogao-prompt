# GaoGao Prompt Templates - 可复用提示词模板

> 使用时替换 [方括号] 中的变量。模板是起点，不是终稿；先用 `prompt-recipes.md` 选策略，再删掉无关元素，并补上具体镜头、光照、材质、构图、约束和参数。

## 使用索引

- 产品摄影：主图、白底图、爆炸视图
- 护肤品广告：柔和、晨间、补水、抗衰、微缩创意
- 电商营销：详情板、TVC 分镜、广告牌、直播 UI
- 编辑 / 变换：风格迁移、试衣、移除、光照天气
- 创意 / 插画：表情网格、电影感、手绘信息图、结构化渲染

---

## 一、产品摄影

### 高端产品工作室图

```
Create a premium product studio image of [产品名称] for [品牌名].

Show the product floating/standing against a clean light gray to soft white
gradient background with a minimal high-end aesthetic.

The product should feel sleek, modern, refined, and premium.
Use a three-quarter front angle so the label and packaging are clearly visible.
Include the brand name cleanly on the product.

Lighting: soft, controlled, editorial, with crisp highlights, soft shadows,
and a subtle colored rim light.
Emphasize material realism and clean geometric forms.

Constraints:
- No extra props, no people, no text overlays, no packaging box
- No distracting elements
- Focus entirely on the product as the hero
- Photorealistic commercial product photography with crisp studio detail
```

### 产品抠图 / 白底图

```
Extract the product from the input image and place it on a plain white
opaque background. Output: centered product, crisp silhouette, no
halos/fringing. Preserve product geometry and label legibility exactly.
Add only light polishing and a subtle realistic contact shadow.
Do not restyle the product; only remove background and lightly polish.
```

### 爆炸视图技术海报

```
Create a premium exploded-view technical poster of [产品名称].
Show every component floating in an elegant spatial arrangement,
connected by thin guide lines to their labeled positions.

Each part should be photorealistic with accurate materials and textures.
Add Chinese annotations for each component.

Background: clean dark gradient.
Style: premium product engineering visualization, Apple-style aesthetic.
Typography: clean sans-serif, white, precise kerning.

Include ONLY this title text (verbatim): "[产品名]"

Constraints:
- No watermarks, no logos of other brands
- Accurate component proportions
- Professional commercial quality
```

---

## 二、护肤品广告

护肤品广告必须使用 BOSS 或品牌方提供的产品名、成分、功效、规格、价格和文案。不要编造功效数据、成分表、备案编号、临床证明、认证标识或品牌 Logo。

### 柔和护肤品广告

```
A soft [瓶身颜色] bottle with a [泵头颜色] pump stands on a matte podium,
surrounded by silky foam and [花卉名称].
The background is a [背景色] gradient with subtle bubble details.
The label emphasizes only the supplied text: [核心成分] and [护肤理念].
Fresh [花卉名称] flowers accentuate the gentle appeal.

Style: premium skincare advertising, soft diffused lighting,
clean [色系] palette, photorealistic commercial beauty photography.

Constraints:
- Use only supplied product claims and label text
- No invented ingredients, efficacy data, certification marks, registration numbers, or fake logos
- No extra text unless explicitly supplied
```

### 静奢晨间护肤场景

```
Create a 3:4 vertical beauty lifestyle photograph for a premium
skincare morning routine.

Scene: a travertine bathroom counter beside a soft frosted window,
with a minimal glass serum bottle, ceramic cleanser tube, cream jar,
folded linen towel, jade roller, and a single dewy white camellia flower.

Lighting: natural morning side light, gentle reflections, realistic
glass thickness, soft shadows, clean negative space.

Aesthetic: quiet luxury, Japanese minimalism meets modern spa editorial,
cream / warm stone / translucent pale green palette.

Constraints:
- No visible brand logos
- No readable fake labels except a tiny generic mark "AM ROUTINE"
- No human face, no clutter, no overdone CGI shine
```

### 水感保湿场景

```
A refreshing skincare scene showcasing [产品名].
Crystal-clear water droplets on the product surface, surrounded by
transparent water splashes and fresh blue-green tones.
The background features soft water ripples and light refraction patterns.
A single fresh [植物元素] rests nearby.

Lighting: bright, clean, natural daylight feel.
Style: hydrating freshness, premium Korean skincare advertising,
dewy and translucent aesthetic, photorealistic.

Constraints:
- Use only supplied product claims and label text
- No invented hydration percentages, timelines, ingredient tables, or medical claims
```

### 奢华抗衰场景

```
A luxurious anti-aging skincare scene with [产品名] as the hero.
Rich champagne gold and deep navy color palette.
The product sits on a polished dark marble surface with subtle gold veining.
Surrounding elements: pearl-like luminous spheres, delicate collagen
protein strands, subtle light refraction suggesting firmness and elasticity.

Lighting: dramatic warm golden light from upper left, deep shadows.
Style: high-end luxury skincare campaign, mature elegance,
professional anti-aging technology feel, photorealistic.

Constraints:
- Use only supplied product claims and label text
- No invented anti-aging efficacy data, clinical claims, ingredient tables, or certification marks
```

### 微缩透视广告（创意）

```
A hyper-realistic miniature diorama product advertisement featuring
an oversized luxury skincare pump bottle labeled "[BRAND] – [PRODUCT]"
in cream/beige with a polished gold pump top, placed on a circular platform.

Tiny figurine construction workers dressed in yellow coveralls and white
hard hats swarm around the bottle climbing scaffolding, painting the
bottle with rollers, operating a tower crane.

The overall color palette is warm beige, cream, gold, and mustard yellow.
Studio photography style with soft diffused lighting, clean beige background.

Style: tilt-shift miniature aesthetic, intricate miniature detailing,
commercial product photography, photorealistic CGI render.
```

---

## 三、电商营销

电商营销模板适合结构化布局，但最终 prompt 不能编造价格、销量、功效、对比数据、备案信息或法律合规文字。没有提供的数据必须省略或改成抽象视觉。

### 中国电商营销板（JSON 结构化）

```json
{
  "type": "Chinese e-commerce product marketing board",
  "product": {
    "category": "[品类]",
    "brand": "[品牌名]",
    "name": "[产品名]",
    "packaging": "[包装描述]",
    "net_weight": "[规格]"
  },
  "style": {
    "overall": "premium skincare advertising layout",
    "color_palette": ["cream", "warm gold", "soft white", "beige"],
    "lighting": "soft studio lighting with gentle highlights",
    "mood": "luxurious, gentle, hydrating, trustworthy"
  },
  "text_policy": {
    "allowed_text": "only user-supplied product name, short claims, section titles, and legal-safe copy",
    "forbidden_text": "invented efficacy data, ingredient tables, registration numbers, medical claims, fake logos"
  },
  "layout": {
    "format": "single tall composite board divided into sections",
    "sections": [
      {"title": "主图", "count": 1},
      {"title": "核心卖点", "count": 3},
      {"title": "使用方式 HOW TO USE", "count": 3},
      {"title": "品牌理念", "count": 2}
    ]
  }
}
```

### TVC 分镜脚本（9 宫格）

```
Using the provided reference image, transform the single product photo
into a polished e-commerce TVC storyboard for a [时长]-second ad in
[比例] format, presented as a 9-panel grid.

Keep the same product as the base, but restage it across cinematic
advertising shots with warm premium lighting, shallow depth of field,
and a refined lifestyle environment.

Add a dark storyboard layout with Chinese titles and timing for each panel.
Include exactly 9 scenes:
1) Environment-establishing wide shot
2) Hero product medium shot
3) Extreme close-up of texture
4) Use case showing product in action
5) Feature display
6) Ingredient/technology scene
7) Detail close-up
8) Lifestyle scene
9) Brand closing frame with marketing text
```

### 户外广告牌 Mockup

```
Create a realistic billboard mockup of [产品] on a [场景] during [时间].
Billboard text (EXACT, verbatim, no extra characters):
"[广告文案]"
Typography: bold sans-serif, high contrast, centered, clean kerning.
Ensure text appears once and is perfectly legible.
No watermarks, no extra logos.
```

### 电商直播 UI Mockup（JSON 结构化）

```json
{
  "type": "live stream UI mockup",
  "subject": {
    "description": "portrait of [主播描述]",
    "background": "[背景描述]"
  },
  "ui_overlay": {
    "top_header": {
      "host_info": "avatar, name '[主播名]', subtext '[点赞数]本场点赞', red '关注' button"
    },
    "bottom_left_chat": {
      "messages": ["[弹幕1]", "[弹幕2]", "[弹幕3]"]
    },
    "bottom_right_product_card": {
      "hot_tag": "orange '热卖 x [数量]'",
      "image": "[产品描述]",
      "title": "[产品名]",
      "price": "¥[价格]",
      "button": "red '抢' button"
    }
  }
}
```

---

## 四、编辑 / 变换

### 风格迁移

```
Use the same style from the input image and generate [新场景描述].
Maintain the exact visual language: color palette, texture, brush strokes,
grain, and overall aesthetic.
Do not add watermarks, text, or logos.
```

### 虚拟试衣

```
Keep the person in the input image exactly the same — same face, body type,
pose, hairstyle, expression, and skin tone.
Only change their clothing to: [服装描述].
The new clothing should fit naturally with realistic draping, folds, and occlusion.
Match the original lighting, shadows, and color temperature.
Do not add accessories, text, logos, or watermarks.
```

### 物体移除

```
Remove [要移除的物体] from the image. Do not change anything else.
```

### 光照 / 天气变换

```
Change ONLY the environmental conditions of this image:
- New lighting: [光照描述]
- New atmosphere: [氛围描述]
- New shadows: [阴影描述]

Keep the identity, geometry, camera angle, and object positions
exactly the same. Do not add or remove any objects.
```

---

## 五、创意 / 插画

### 16 格表情网格

```
Create a 16-panel expression grid of [角色描述].
Face shape, hairstyle, and clothing must remain highly consistent
across all panels.
The 16 expressions: happy, sad, angry, surprised, shy, speechless,
evil grin, contemplative, curious, proud, wronged, disdainful,
confused, scared, crying, and heart expression.
Style: [anime / polished 3D animated feature render / chibi]
```

### 电影感视觉特征

```
A cinematic wide shot using these visual traits: [构图方式], [镜头语言],
[场景密度], [材质质感], [边缘处理], [氛围关键词].
[场景描述]
The lighting is [光照描述].
The color palette is '[调色板名称]': [具体色彩描述].
```

视觉特征速查：
- 对称粉彩：完美居中构图、粉彩色调、玩偶屋式布景、平面化人物站位
- 巨构科幻：极大尺度建筑、沙尘橙色、工业单色、低人物占比
- 霓虹黑色电影：琥珀 + 钴蓝双色调、有毒橙色雾、雨夜反射、强背光
- 手绘动画感：水彩水粉质感、柔和画家边缘、可见笔触、温暖自然光

### 手绘信息图

```
一张手绘风格的[主题]信息图。
[色调描述]。
标题用书法体："[标题]"。
标注至少[数量]个地标/元素，每个配小插画和名称。
底部图例用简洁图标说明分类。
风格：手绘水彩+钢笔线稿，[杂志/图鉴]质感。
```

### JSON 结构化食品/产品渲染

```json
{
  "ENVIRONMENT": {
    "Background": "Gradient([背景色])",
    "Atmospheric_FX": ["Floating_Particles", "Depth_Blur", "Cinematic_Bokeh"],
    "Lighting": {
      "Type": "Directional_Studio_Warmer",
      "Highlights": "Specular_Glossy_Reflections",
      "Shadow_Softness": "High"
    }
  },
  "CORE_ASSETS": {
    "Primary_Subject": "[主体]",
    "Physics": "[物理效果]",
    "Material_Properties": {
      "Outer": "[外层材质]",
      "Surface_Texture": "[表面纹理]",
      "Interior_Cross_Section": {
        "Structure": "[内部结构]",
        "Core": "[核心填充]"
      }
    }
  },
  "PARTICLE_SYSTEMS": [
    {"Object": "[漂浮物1]", "State": "Floating"},
    {"Object": "[漂浮物2]", "State": "Fragmented"}
  ],
  "RENDER_OUTPUT": {
    "Target_Size": "[1024x1536 / 1536x1024 / 2560x1440]",
    "Aspect_Ratio": "3:4",
    "Quality_Flags": ["Photorealistic", "Sharp_Foreground", "Clean_Material_Detail"]
  }
}
```
