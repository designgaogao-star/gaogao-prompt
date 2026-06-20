# 任务板

最后更新：2026-06-20

| Task | Owner | Status | Reviewer | Write Scope | Notes |
|---|---|---|---|---|---|
| T-000 | 项目总管 | waiting | 项目总管 | Agent Office public files | 等待 BOSS 安排下一个 skill 制作或维护任务；当前不自动开工。 |
| T-001 | 项目总管 | done | 项目总管 | `gaogao-prompt/`, `C:\Users\79974\.codex\skills\gaogao-prompt\`, Agent Office public files | 已升级为 prompt director，新增 recipes/settings/style/examples，已同步安装并校验通过。 |
| T-002 | 项目总管 | done | 项目总管 | `gaogao-prompt/`, `dist/`, Agent Office public files | 发布就绪审计完成；skill 名保持不变，发布包/manifest/report 已生成，最终 release audit PASS。 |
| T-003 | 项目总管 | done | 项目总管 | `gaogao-prompt/`, `dist/`, installed skill copy, Agent Office public files | 全面检测完成；修复过期 OpenAI Images API reference 来源链接，重建发布包并复验 PASS。 |
| T-004 | 项目总管 | done | 项目总管 | `C:\Users\79974\Documents\Codex\2026-06-08\goal-codex-codex\outputs\gaogao-office-skill\`, `C:\Users\79974\.codex\skills\gaogao-office\`, `outputs/gaogao-office-skill.zip`, Agent Office public files | 接手旧对话 `019ea501-0cf2-7c23-8505-699c13519519`；完成 GaoGao Office v1.1.1 任务板瘦身补丁、zip parity、安装版同步、commit `91fcf7e`、tag/push 和 GitHub release。 |
| T-005 | 项目总管 | active | 项目总管 | `gaogao-prompt/`, `dist/`, root release docs, `C:\Users\79974\.codex\skills\gaogao-prompt\`, Agent Office public files, GitHub repo `designgaogao-star/gaogao-prompt` | GaoGao Prompt v1.0.0 GitHub 正式发布中；README/CHANGELOG/release notes 已准备，新包与 manifest 已刷新，本地/安装/解压 quick validate 已通过，等待 GitHub repo/tag/release 发布验证。 |

## 任务规则

- 每项任务必须有 owner、reviewer、写入范围和验收方式。
- 多员工任务默认由项目总管拆分和派工；员工完成后回给项目总管，由项目总管统一汇报 BOSS。
- 派工并发按 `office-plan.json` 的 `dispatch_policy` 执行；本机容量未知或偏低时，一次只派一个员工。
- 如果任务变复杂，再拆出单独任务文件或归档记录。
