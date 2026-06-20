# GaoGao Prompt Craft Rules - 21 条提示词工艺原则

> 整理自 GPT Image 2 实战提示词经验，经电商产品图、海报、编辑和创意插画场景补充。

---

## 目录

- 原则 0-5：参考、精确文字、摄影语言、写实声明、质量档位
- 原则 6-12：迭代、不变量、编辑、人物、约束、JSON、动态参数
- 原则 13-18：多参考、氛围、负面约束、参考图、分镜、风格特征
- 原则 19-21：保真优先级、提示词密度、图后复盘
- 综合检查清单
- 反模式与修复

## 原则 0：先参考，不从零写

起草提示词前先在已加载的 recipes、examples 或 templates 中找是否有匹配案例可复用。除非用户明确要求查整个提示词库，否则不要为了找模板而加载全部参考。

## 原则 1：精确文字用引号包裹

所有需要在图片中显示的文字，用引号包裹。声明 "EXACT, verbatim, no extra characters"。

## 原则 2：难写的词逐字母拼写

品牌名、不常见拼写的词，逐字母给出：`"A-U-R-A-E"` 而非 `"AURAE"`。

## 原则 3：用摄影语言控制写实感

镜头（50mm lens）、光照（soft coastal daylight）、取景（medium close-up at eye level）比通用的 "8K/ultra-detailed" 更可靠。

具体可用词汇：

```
镜头: 24mm / 35mm / 50mm / 85mm / 100mm macro
光圈: f/1.2 / f/1.8 / f/2.8 / f/5.6 / f/8
光照: soft diffused, hard directional, golden hour, overcast, rim light,
      top-down studio, 45-degree key light, backlit silhouette
构图: eye-level, bird's-eye, worm's-eye, Dutch angle, over-the-shoulder
```

## 原则 4：照片级写实必须显式声明

在提示词中包含 "photorealistic" 一词强力激活写实模式。"real photograph"、"taken on a real camera" 也有帮助。

## 原则 5：质量等级是预算旋钮

- `low` = 廉价草稿 / 大量变体探索
- `medium` = 正常探索 / 风格试探
- `high` = 最终海报 / 中文文字 / 图表 / Banner

先 low 跑一轮评估，很多场景 low 已足够好。只对最终交付物用 high。

## 原则 6：迭代优于过载

从干净基础开始，用小的单一变更迭代。不要在一个提示里塞太多要求。每次只改 1-2 个变量。

## 原则 7：每次迭代重复不变量

不要假设模型会记住。每次编辑都重新声明需要保留的元素。完整列出，不要省略。

## 原则 8：编辑用"只改 X + 保留其他"

`"change only X" + "keep everything else the same"` 是编辑的基本模式。同时列出所有保留项：几何形状、标签文字、Logo、构图、光照方向。

## 原则 9：人物描写要具体

比例、身体取景、目光方向、物体互动。"full body visible, feet included"、"looking down at the book, not at the camera"。不要模糊的"beautiful woman"。

## 原则 10：约束条件要明确

排除项：`"no watermark"`, `"no extra text"`, `"no logos/trademarks"`
保留项：`"preserve identity/geometry/layout/brand elements"`

双面写，不要只写一面。

## 原则 11：JSON 结构化复杂场景

复杂的多元素场景（电商套图、信息图、广告板）使用 JSON 格式精确控制布局、风格、元素。将环境、主体、粒子系统、渲染输出分层定义。

## 原则 12：动态参数创建可复用模板

`{argument name="xxx" default="yyy"}` 格式让提示词变成可填充模板，方便批量套用。

## 原则 13：多图输入要索引引用

`"Image 1: product photo... Image 2: style reference..."` + 描述它们如何互动。不要只说"the images"。

必须给每张图分配角色：

```text
Image 1 = product identity and label
Image 2 = style palette and lighting
Image 3 = layout/composition
Image 4 = material/prop reference
```

冲突时按优先级处理：

1. 产品/人物身份、几何形状、标签、Logo、精确文字
2. 布局和镜头构图
3. 光照、调色、材质
4. 氛围、装饰、道具

未分配角色的参考图细节不要泄漏进最终画面。

## 原则 14：氛围场景额外补充细节

宽幅 / 电影感 / 低光 / 霓虹场景中，模型可能为追求表面写实而牺牲氛围。显式补充：

```
Maintain deep shadows and high contrast.
Do not brighten the scene; keep the moody low-key lighting.
Rich dark tones with selective highlights only.
```

## 原则 15：负面约束同样重要

明确说不要什么：`"No text, logos, people, hands, cartoon style, or plastic-looking food"`

不要只正面描述，负面约束往往更关键。

## 原则 16：参考图像结合编辑

用 `"use the uploaded image"` 结合参考照片进行风格转换，保持参考图的视觉语言。编辑模式比纯生成模式对产品保真度更高。

## 原则 17：分镜思维

不仅生成单图，可生成完整套图：主图 + 详情页 + 分镜脚本。电商项目建议以系列为单位规划，而非单图作战。

## 原则 18：风格引用要翻译成视觉特征

不要只写 "in the style of X"。把参考风格落到可观察的画面特征：构图、镜头、色彩、材质、笔触、颗粒、光比、场景密度、人物比例、边缘处理、排版方式。最终 prompt 应该即使删掉参考名也能成立。

## 原则 19：保真优先级要明示

编辑和多参考任务必须写出保真优先级。产品图通常是：

```text
Preservation priority:
1. product geometry, label text, logo position, color, proportions
2. camera perspective and visible product face
3. lighting/reflection consistency
4. background style and props
```

人物图通常是：

```text
Preservation priority:
1. face identity, body type, skin tone, hairstyle
2. pose, gaze, expression
3. clothing fit and occlusion
4. background and atmosphere
```

## 原则 20：提示词密度要可控

最终 prompt 里最多保留一个主视觉想法、一个主风格、一个主构图、一个主光照方案。超过 3 个主要创意点时，拆成风格锚点、单图 prompt 或分步编辑。

## 原则 21：图后复盘要找失败原因

看到生成图后，不要只说"再高级一点"。先判断失败类型：

- prompt ambiguity：描述太泛
- overload：要求太多
- preservation drift：保真声明不够
- reference conflict：参考图角色冲突
- text risk：文字太长或没锁定
- model limitation：结构布局或文字精度超出稳定范围

下一轮只改 1-2 个变量，并重复所有保留项。

---

## 综合检查清单

写完提示词后过一遍：

- [ ] 四块结构是否完整？（场景→主体→细节→约束）
- [ ] 用了摄影术语还是通用质量词？
- [ ] 约束条件是否双面（排除+保留）？
- [ ] 需要图内文字时是否用了引号 + verbatim？
- [ ] 产品保真声明是否包含？（电商场景）
- [ ] quality 档位是否合理？
- [ ] 是否一次性塞了太多要求？（超过 3 个主要变更 → 拆分迭代）
- [ ] 是否还有未替换的 [方括号] / 模板痕迹？
- [ ] 风格参考是否已经翻译成可观察画面特征？

## 反模式与修复

| 反模式 | 风险 | 修复 |
|---|---|---|
| `8K ultra-detailed masterpiece` | 空泛质量词，控制力弱 | 换成镜头、光照、材质、构图 |
| `高级、好看、氛围感` | 画面不可执行 | 翻译成具体光线、材质、留白、色温 |
| 多个艺术风格同时出现 | 风格互相打架 | 只保留一个主视觉语言 |
| `Include ONLY this text` 但又要保留产品标签 | 会误删/破坏标签 | 区分 poster overlay text 和 product label text |
| 未提供功效数据却要求详情页 | 容易编造 claim | 只用用户提供的卖点，其他用抽象视觉 |
| `keep everything the same` 同时要求换场景 | 自相矛盾 | 写清 allowed changes 与 locked attributes |
| 多参考图只说 "use these images" | 参考泄漏或冲突 | 为每张图指定角色和优先级 |
| 长中文文案进图 | 容易错字/排版失败 | 生成无字底图，后期排版 |
| 产品广告里道具过多 | 主体弱、廉价感 | 限制 1-3 个相关道具 |
| 系列图每张都换光线/镜头 | 系列不统一 | 建 style anchor ledger，每张只变一个变量 |
