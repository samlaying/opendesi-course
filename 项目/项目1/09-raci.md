# RACI

R 执行 · A 拍板 · C 协商 · I 知情。一人开发时四列可兼任（本人 = PM+Designer+Engineer），仍要写清 Agent 不能自行发布。

| 事项 | PM(本人) | Designer(本人) | Engineer(本人) | Agent(Claude) |
|---|---|---|---|---|
| Product Context 更新 | A | C | C | R 起草（禁区见 Context「Agent 不准自行发明的规则」） |
| Design System 更新 | C | A | C | R 起草（token/规则改动需人过目） |
| Prototype 能否进开发 | A | C | I | I（只提交，不判定） |
| 主路径实现 | C | I | A | R（e2e 证据随交付） |
| 打卡数据 / streak | A | — | — | **禁止触碰**：不得代打卡、不得改计算规则 |
| 上线 / 对外发布 | A | I | A | **不得自行发布**：不 deploy、不提交 git、不发任何平台 |
| 本页 RACI 修改 | A | I | I | I |
