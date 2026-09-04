# 第4章 把设计规则说清楚：建立 Design System

**核心问题：** 怎么告诉 AI 应该怎么设计。视觉、组件、布局、交互、状态、业务规则，变成可读资产。

**上一章接口：** Context 已冻结范围。本章只覆盖「这 3 个页面够用」的规则，禁止堆大厂全量 DS。  
**下一章接口：** Agent 必须能打开本包，而不是只看截图。

## 一页概念

人能看懂的规范，模型不一定能用。可给 Agent 的 DS 至少要有：

- **Token：** 色 / 字 / 间距的命名，而不是一串散落 hex  
- **组件：** 名称、状态（默认/悬停/禁用/加载/空）、何时用  
- **布局与层级：** 页头、主区、反馈出现在哪  
- **业务规则进界面：** 例如「未登录不能收藏」必须写成状态，而不是藏在 PRD 角落  

语料中的分层（安那纳拉 · `68d32ecd000000001101f869`）：原始值 → Primitive → Semantic →（可选）Component。优先复用 semantic，不要每个组件私有一套色。

## 当堂资产：最小包（只够 3 页）

### Tokens

| 层级 | 名字 | 值 | 用在 |
|---|---|---|---|
| primitive | color.gray.100 | | 底 |
| semantic | color.surface.default | | 页面背景 |
| semantic | color.text.primary | | 正文 |
| semantic | color.action.primary | | 主按钮 |
| spacing | space.4 / 8 / 16 / 24 | | 间距只准用这一档 |

命名参考：`{Category}.{Property}.{Variant}.{State}`，例如 `color.text.primary.hover`。

### 组件清单

| 组件 | 状态 | 用 / 不用 |
|---|---|---|
| Button | default / hover / disabled / loading | 主操作只用 primary |
| Input | default / error / disabled | 错误文案在字段下 |
| ListRow | default / empty | 空态有一句说明 + 一个行动 |

### 规则（给 Agent 的硬约束）

```
1. 主按钮每屏最多一个。
2. 间距只使用 space token，禁止随意 px。
3. 空态、加载、失败三种状态必须画进页面清单。
4. 未经 Context 允许，不得新增导航项。
```

作业：给第3章 Context 配这一包，输出「只够 3 个页面」的规范文件（Markdown 或 Tailwind 注释区均可）。

## 语料案例

1. **design tokens 101 怎么命名** · 安那纳拉 · `68d32ecd000000001101f869`  
2. **分享用 Claude 搭 design system 思路** · 肥可乐不喝可乐 · 检索 `Design System 搭建`  
3. **如何理清一团乱麻的设计系统** · 同上作者 · 用来讲存量规范，接第7章  
4. **Vibe Coding 必存：开源 UI 组件库** · Rylee歪理 · 只作组件来源，不替代你的规则文档  

语料里还有 Tailwind / 组件库文档词，适合当「代码级 DS」示例。
