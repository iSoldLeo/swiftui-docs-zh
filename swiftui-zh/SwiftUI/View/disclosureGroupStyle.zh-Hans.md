--- 来源：https://developer.apple.com/documentation/SwiftUI/View/disclosureGroupStyle(_:)

抓取时间：2025-11-30T21:18:34Z

---

#disclosureGroupStyle(_:)

**实例方法**

设置此视图中披露组的样式。

## 声明

```swift
nonisolated func disclosureGroupStyle<S>(_ style: S) -> some View where S : DisclosureGroupStyle

```

## 逐步披露信息

- **OutlineGroup**：一种结构，可根据底层树状结构化、已识别的数据集合按需计算视图和披露组。

- **DisclosureGroup**：一种视图，可根据披露控件的状态显示或隐藏其他内容视图。


---
source: https://developer.apple.com/documentation/SwiftUI/View/disclosureGroupStyle(_:)
crawled: 2025-11-30T21:18:34Z
---

# disclosureGroupStyle(_:)

**Instance Method**

Sets the style for disclosure groups within this view.

## Declaration

```swift
nonisolated func disclosureGroupStyle<S>(_ style: S) -> some View where S : DisclosureGroupStyle

```

## Disclosing information progressively

- **OutlineGroup**: A structure that computes views and disclosure groups on demand from an underlying collection of tree-structured, identified data.
- **DisclosureGroup**: A view that shows or hides another content view, based on the state of a disclosure control.

