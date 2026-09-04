# Design System · 只够本产品 3 页

先有 [03-product-context.md](03-product-context.md) 再填。这是**你要做的产品**的视觉和规则，不是 OpenPencil 编辑器外壳。

## Tokens

| 层级 | 名字 | 值 | 用在 |
|---|---|---|---|
| primitive | | | |
| semantic | color.surface.default | | 页面背景 |
| semantic | color.text.primary | | 正文 |
| semantic | color.action.primary | | 主按钮 |
| spacing | space.4 / 8 / 16 / 24 | | 间距只准用这一档 |

## 组件清单

| 组件 | 状态 | 用 / 不用 |
|---|---|---|
| Button | default / hover / disabled / loading | 主操作只用 primary |
| Input | default / error / disabled | 错误文案在字段下 |
| ListRow | default / empty | 空态有一句说明 + 一个行动 |

## 规则（给 Agent）

```
1. 主按钮每屏最多一个。
2. 间距只使用 space token。
3. 空态、加载、失败必须进页面清单。
4. 未经 Context 允许，不得新增导航项。
```
