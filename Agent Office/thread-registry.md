# 线程登记表

最后更新：2026-06-09

当前项目经理窗口标题：`项目总管`

| Role | Thread Title | Thread ID | Mode | Current Assignment | Write Scope | Status |
|---|---|---|---|---|---|---|
| 项目总管 | 项目总管 | 019ea823-9de3-76c2-810e-096848032029 | local | 等待 BOSS 安排下一个 skill 制作或维护任务。 | Agent Office 公共文件、AGENTS.md、Agent Office/Employees/pm/，以及 BOSS 明确批准的 skill 文件。 | 项目总管 |

## 员工续任 / 重启提示词

> 这些提示词用于员工入职、换窗口续任或角色恢复。办公室挂牌、AGENTS.md 应用和旧资料入库完成前，不要发送这些提示词。

BOSS 授权正式接管后，项目总管会先确认自己已经挂牌，再安排需要独立窗口的员工入职。员工已入职后，本区也可作为以后重建窗口时的启动材料。

项目总管先给当前窗口挂牌，再邀请员工入职。Codex 桌面有线程工具时优先自动创建员工对话；工具不可用时，才手动复制下面的 `text` 代码框。

当前窗口默认已接任项目总管，不需要再为项目总管开一个窗口。

### 项目总管续任提示词

如果当前项目总管窗口丢失或需要重开，用下面提示词恢复。

```text
本对话角色：项目总管

你现在接任这个项目的「项目总管」。第一轮只做续任确认，不主动开工。

项目：Skill制作
项目根目录：E:\codex\Skill制作
默认语言：中文。路径、任务 ID、status enum、代码标识保持原样。

请先读取：
1. AGENTS.md
2. Agent Office/README.md
3. Agent Office/status.md
4. Agent Office/project-brief.md
5. Agent Office/task-board.md
6. Agent Office/thread-registry.md
7. Agent Office/Employees/pm/README.md
8. Agent Office/Employees/pm/memory.md
9. Agent Office/Employees/pm/current-task.md

第一轮请用 5-8 行确认：
1. 你是谁
2. 当前项目是什么
3. 你负责什么
4. 当前等待什么派工
5. 如需开工，需要 BOSS 给什么输入

之后等待 BOSS / 用户派工。完成正式任务后，先更新 Agent Office 公共文件、自己的 memory.md 和 current-task.md，再向 BOSS 汇报。需要员工协作时，由 project manager / 项目总管拆分任务并派工。
```

## 派工并发策略

capacity-aware controller dispatch；最多同时派工 3 个员工。本机容量较充足；当前没有额外员工，后续扩编时最多同时派三个员工，除非 BOSS 另行批准。

项目总管可以一次邀请所有员工入职，但正式派工要按这个并发上限执行；本机容量未知或偏低时，一个员工完成后再派下一个。

## 项目总管派工协议

BOSS 默认只需要和项目总管窗口对话。项目总管判断任务是否需要员工；需要时，先更新任务板和员工 current-task，再把下面这种派工消息发给员工窗口。

```text
本次派工：{任务编号或一句话任务}
请先读取 AGENTS.md、Agent Office 公共文件，以及你自己的员工文件夹。
写入范围：{明确路径或范围}
交付内容：{期望输出}
完成后请更新你的 memory.md 和 current-task.md，然后把结果回复给项目总管。
```

暂无需要新建的员工窗口。
