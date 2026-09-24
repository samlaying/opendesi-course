# SOP

每周一次迭代（周日晚上 30 分钟），顺序不可跳：

1. 更新 [00-readme.md](00-readme.md) 和 [03-product-context.md](03-product-context.md)——先改认知，再动手
2. 更新 [04-design-system.md](04-design-system.md)（只覆盖本周要动的页面，不预设计）
3. 结构清单 → 人签字 → Prototype（[05](05-agent-run.md)）——给 Agent 的开场指令固定为：
   ```
   读 项目/项目1/03-product-context.md 和 04-design-system.md，
   按本周页面清单出结构，先不要写代码。改完结构等我签字。
   ```
4. 可运行后填 [06](06-mvp-checklist.md)——e2e 脚本放 `/tmp` 重跑或存入 `app/`，证据写进表格
5. 反馈写 [08](08-iteration-log.md)，至少 1 条回写 Context 或 DS（本周已完成 2 条：多动作留白、a11y 列）

## 结业包目录（第 10 章作业）

- [x] 00 基本信息 · [x] 03 Context · [x] 04 DS · [x] 05 工作流记录 · [x] 06 MVP 清单
- [x] 07 存量改造（绿场确认不适用） · [x] 08 迭代日志 v0.1 · [x] 09 RACI · [x] SOP（本页）
- [x] `prototype/` 低保真 · [x] `app/` 可运行 MVP（`open app/index.html`）

项目1 文档链 2026-09-12 全部闭环，进入「用起来→收反馈→回写」循环。
