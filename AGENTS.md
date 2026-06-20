# AGENTS.md

## GaoGao Office Protocol

本仓库使用 `Agent Office/` 作为长期 Agent 项目办公室。

开始项目工作前：
- 先读 `Agent Office/README.md`、`Agent Office/status.md`、`Agent Office/project-brief.md` 和 `Agent Office/task-board.md`。
- 如果你被分配了角色，读取公共区和 `Agent Office/Employees/{role-slug}/` 里属于自己的员工文件夹。
- 不要读取其他员工文件夹，除非用户明确要求维护、审计或恢复办公室。
- 日常工作不要读取 `Agent Office/Archive/Old Project Memory/`；那里是已吸收旧知识的历史档案。

协作规则：
- 当前窗口默认是第一任项目总管，负责给办公室挂牌、路由任务、更新公共区和处理迁移收尾。
- 多员工模式默认由项目总管做单入口总控：BOSS 主要和项目总管对话，项目总管拆任务、派给员工窗口、回收结果并统一汇报。
- 员工数量不等于并发数量；项目总管按 `Agent Office/office-plan.json` 的 `dispatch_policy` 控制同时派工数量。
- `Agent Office/thread-registry.md` 是长期 Agent 员工名册和入职提示记录。
- 跨角色请求、答复和交接写入 `Agent Office/communication.md`。
- 当前任务和责任人写入 `Agent Office/task-board.md`。
- 员工完成有意义工作后，先更新自己的 `memory.md` 和 `current-task.md`，再向项目总管汇报。
- 只有项目总管、BOSS 或被明确授权的员工才更新公共状态。
- 结束任务时说明改了什么、验证了什么、还剩什么、下一个负责人是谁。
