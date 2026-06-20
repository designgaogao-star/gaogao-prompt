# 项目地图

状态：已完成首次只读体检
最后更新：2026-06-09

## 文件地图

项目根目录：`E:\codex\Skill制作`

当前活跃内容：

- `gaogao-prompt/SKILL.md`：GaoGao Prompt skill 主入口，负责触发说明、工作流、输出格式和核心提示词规则。
- `gaogao-prompt/references/prompt-recipes.md`：提示词导演配方体系，负责模式选择、场景 recipe 和修复策略。
- `gaogao-prompt/references/model-settings.md`：GPT Image / GPT Imagine 设置参考和 GPT Imagine 别名策略。
- `gaogao-prompt/references/style-vocabulary.md`：镜头、光照、构图、材质、调色和反失败约束词库。
- `gaogao-prompt/references/examples.md`：高难 prompt rescue、产品编辑、海报方向和系列图的标杆例子。
- `gaogao-prompt/references/templates.md`：可复用提示词模板库。
- `gaogao-prompt/references/craft-rules.md`：提示词工艺原则和检查清单。
- `gaogao-prompt/agents/openai.yaml`：Codex skill UI 元数据。

办公室内容：

- `Agent Office/`：本项目长期 Agent 办公室。
- `AGENTS.md`：根目录 Agent 协作入口，已由 GaoGao Office 正式应用。

发布内容：

- `dist/gaogao-prompt-2026-06-09.zip`：可发布 skill 包，顶层目录为 `gaogao-prompt/`。
- `dist/gaogao-prompt-v1.0.0.zip`：GitHub v1.0.0 正式发布包，顶层目录为 `gaogao-prompt/`。
- `dist/gaogao-prompt-release-manifest.json`：发布 manifest，包含包 SHA-256、文件哈希、校验证据和 UTF-8 校验要求。
- `dist/gaogao-prompt-release-report.md`：人工可读发布报告。
- `dist/gaogao-prompt-v1.0.0-release-notes.md`：GitHub release body 文案。
- `README.md` / `CHANGELOG.md`：仓库根目录公开说明和版本记录，不进入 skill payload。

## 已吸收的旧资料

暂无旧管理资料。首次体检未发现 `README.md`、旧 `AGENTS.md`、`vibe/`、planning 文档或其他旧项目记忆。

## 项目状态线索

- 当前项目将作为 `designgaogao-star/gaogao-prompt` 的 GitHub 发布仓库；旧 `.git` 目录为空，需要初始化有效 Git 仓库。
- 当前核心产物已安装到 `C:\Users\79974\.codex\skills\gaogao-prompt`。
- `gaogao-prompt` 本地副本和安装副本均已通过 `quick_validate.py` 校验。
- 发布包解压后也通过 `quick_validate.py`；Windows 校验需使用 `python -X utf8` 或 `PYTHONUTF8=1`。

## 不读取内容的材料

图片、视频、二进制文件、疑似敏感文件和依赖/构建目录只记录文件名或跳过内容读取。
