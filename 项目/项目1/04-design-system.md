# Design System · FitLog（健身打卡记录）

先有 [03-product-context.md](03-product-context.md) 再填。这是**FitLog**的视觉和规则，只覆盖第一版 3 个视图：今日、记一笔、月视图。

## 设计立场

健身是汗和铁的事，界面要**冷静、不喊叫**：暖白底、一个能量橙做行动、打卡绿只属于成功状态。黑底霓虹风、渐变玻璃态都不做——记录工具的信任感来自稳定，不来自刺激。

## Tokens

| 层级 | 名字 | 值 | 用在 |
|---|---|---|---|
| primitive | gray.900 / 600 / 300 / 100 / 50 | #1A1A1A / #6B6B6B / #C9C9C5 / #EDEDE9 / #FAFAF8 | 文本/边线/底面灰阶 |
| primitive | orange.600 / 500 | #D9480F / #E8590C | 行动色基色 |
| primitive | green.600 | #2F9E44 | 打卡成功 |
| semantic | color.surface.default | gray.50 (#FAFAF8) | 页面背景 |
| semantic | color.surface.card | #FFFFFF | 卡片、表单底 |
| semantic | color.text.primary | gray.900 | 正文、数字 |
| semantic | color.text.secondary | gray.600 | 说明、单位（kg/组） |
| semantic | color.action.primary | orange.500 (#E8590C) | 主按钮（每屏仅一个） |
| semantic | color.action.disabled | gray.300 | 不可用时 |
| semantic | color.state.checked | green.600 | 已打卡标识、月视图实心点 |
| semantic | color.state.backfill | green.600 @ 60% 透明 | 补记点（区别于当日打卡） |
| semantic | color.state.future | gray.100 | 月视图未来日期 |
| semantic | color.state.empty | gray.100 | 月视图未打卡的过去日 |
| spacing | space.4 / 8 / 16 / 24 | 4/8/16/24px | 间距只准用这一档 |
| radius | radius.card / radius.button | 12px / 8px | 卡片圆角大于按钮 |
| font | font.family | system-ui 栈 | 不引入网络字体（离线可用） |
| font | font.size.body / number / caption | 16 / 28 / 13 | 重量数字放大（28）突出 |

## 组件清单

| 组件 | 状态 | 用 / 不用 |
|---|---|---|
| Button | default / pressed / disabled | 「记一笔/保存」用 primary 且每屏仅一个；次要操作（导出）用文字按钮 |
| Segmented | default / selected | 部位选择（胸/背/腿/肩/臂/核心/有氧/其他），选中=action.primary 底白字 |
| InputNumber | default / focus / error | 重量与组数；步进 ±2.5kg；错误文案在字段下方 13px |
| EntryRow | default / backfill | 一条训练记录：动作名+重量×组数；补记条目右侧带「补」角标 |
| StatTile | — | streak 数字卡：大数字 28px + 13px 标签；只读，不做动画 |
| CalendarDot | checked / backfill / empty / future | 月视图单元格 12px 圆点；今天加 2px 描边 |
| EmptyState | — | 一句说明 + 一个行动按钮（如「记第一笔」） |

## 规则（给 Agent）

```
1. 主按钮每屏最多一个，颜色只用 color.action.primary。
2. 间距、圆角、字号只使用 token，禁止引入中间值。
3. 空态、加载、失败必须进页面清单（本地应用无网络加载态，用数据初始化态代替）。
4. 未经 Context 允许，不得新增导航项或页面；底部切换只有 今日 / 月视图 两项。
5. streak、次数等数字一律由数据计算渲染，禁止硬编码示例数字留在成品里。
6. 打卡绿不用于按钮，只用于状态标识（点、角标、对勾）。
7. 破坏性操作（清空数据）必须二次确认，且不用 primary 色。
```
