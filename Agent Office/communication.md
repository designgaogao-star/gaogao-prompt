# 沟通与交接

## 消息规则

- 职责外请求不要直接抢活；先说明应该由哪个员工负责。
- BOSS 的需求默认先进入项目总管；项目总管判断是否自己处理，或拆给员工窗口。
- 需要跨角色处理时，在本文件追加一条消息记录，写清楚 from、to、task、requested response、next owner。
- 任务完成、阻塞、换 owner 或进入 review 时，在本文件追加交接记录。

## Open Messages

暂无。

## Handoffs

### 2026-06-20 T-005 GaoGao Prompt GitHub v1.0.0 发布

- BOSS：批准按计划执行 `gaogao-prompt` 首个 GitHub 正式发版，默认公开仓库 `designgaogao-star/gaogao-prompt`、版本 `v1.0.0`、中英双语文案。
- 项目总管：负责单窗口执行；不派新员工。写入范围包括 release docs、`dist/`、安装副本同步、Agent Office 公共记录和 GitHub 发布动作。
- 验证要求：本地/安装副本/zip 解压副本 quick validate，zip 内容检查，manifest 哈希检查，GitHub repo/release/asset 检查。
- 完成回执：公开仓库 `https://github.com/designgaogao-star/gaogao-prompt` 已创建，tag/release `v1.0.0` 已发布，asset `gaogao-prompt-v1.0.0.zip` 上传成功且 SHA-256 与 manifest 一致。

### 2026-06-09 T-002 发布审查

- Lorentz：指出发布证据缺少 Windows UTF-8 校验要求，默认编码下 `quick_validate.py` 可能因中文触发词报 `UnicodeDecodeError`。
- 处理：manifest 和 release report 已补充 `python -X utf8` / `PYTHONUTF8=1` 要求；重新验证通过。

### 2026-06-09 T-001 子智能体审查汇总

- McClintock：指出模型参数契约、渐进加载、intake matrix、多参考优先级、反模式库等缺口。
- Plato：设计 recipe taxonomy，建议用配方层连接 `SKILL.md`、模板库和工艺规则。
- Kant：压力测试中文海报、游戏海报、产品编辑、6 图系列，确认主要缺口是输出结构。
- Gauss：改后审查发现 `Structured Layout`、`Text Lock`、图片复盘路由和 GPT Imagine 定义缺口；已修复。
