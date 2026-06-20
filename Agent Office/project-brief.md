# 项目简报

项目：Skill制作
生成日期：2026-06-09

## 目标

Maintain a lightweight workspace for creating, installing, and improving Codex skills, starting with the GaoGao Prompt skill.

## 第一里程碑

Keep GaoGao Prompt installable, valid, and easy to iterate, while recording future skill decisions in the office.

## 访谈决策

- 项目类型：Codex skill production and maintenance workspace
- 办公室配置：dynamic
- 办公室版本：0.2.3
- 协作方式：controller-dispatch
- 派工策略：capacity-aware controller dispatch；最多同时派工 3 个员工。本机容量较充足；当前没有额外员工，后续扩编时最多同时派三个员工，除非 BOSS 另行批准。
- 风险等级：low
- 当前角色：项目总管

## 角色决策

当前项目范围集中，先由当前窗口作为项目总管单窗口接管。Skill 编辑和发布检查员暂缓，等多个 skill 或复杂发布流程出现后再入职。

默认协作方式：BOSS 主要和当前项目总管窗口沟通；项目总管按需派工给员工窗口，并把结果整合后汇报。
默认派工策略：员工可以全部入职，但项目总管按本机容量控制并发；配置未知或偏低时一次只派一个员工。

- 项目总管 (`pm`)：统一接收 BOSS 需求，维护 Agent Office 公共记忆、任务板、决策和后续 skill 迭代边界。 职责域：项目办公室维护、skill 制作流程管理、安装校验记录、后续任务拆分和验收汇报。 写入范围：Agent Office 公共文件、AGENTS.md、Agent Office/Employees/pm/，以及 BOSS 明确批准的 skill 文件。 当前窗口接任。

## 暂不创建的角色

- Skill 编辑：后续负责重构 skill 说明、模板和规则。
- 发布检查员：后续负责安装、校验和发布前风险清单。
