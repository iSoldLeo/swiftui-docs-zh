--- 来源：https://developer.apple.com/documentation/SwiftUI/HorizontalAlignment/listRowSeparatorTrailing
抓取时间：2025-12-03T06:36:41Z

---

# listRowSeparatorTrailing

**类型属性**

用于标记行分隔符尾端的参考线。

## 声明



## 说明

使用此参考线可将底部行分隔符的尾端与单元格内容视图中的任何其他水平参考线对齐。

要更改行分隔符的可见性或色调，请分别使用 DL_0006 和 DL_0005。

## 获取参考线

- **leading**：用于标记视图前缘的参考线。

- **center**：用于标记视图水平中心的参考线。

- **trailing**：用于标记视图后缘的参考线。

- **listRowSeparatorLeading**：用于标记 `List` 行分隔符前缘的参考线。


---
source: https://developer.apple.com/documentation/SwiftUI/HorizontalAlignment/listRowSeparatorTrailing
crawled: 2025-12-03T06:36:41Z
---

# listRowSeparatorTrailing

**Type Property**

A guide marking the trailing edge of a `List` row separator.

## Declaration

```swift
static let listRowSeparatorTrailing: HorizontalAlignment
```

## Discussion

Use this guide to align the trailing end of the bottom `List` row separator with any other horizontal guide of a view that is part of the cell content.

To change the visibility or tint of the row separator use respectively [listRowSeparator(_:edges:)](../View/listRowSeparator___edges.zh-Hans.md) and [listRowSeparatorTint(_:edges:)](../View/listRowSeparatorTint___edges.zh-Hans.md).

## Getting guides

- **leading**: A guide that marks the leading edge of the view.
- **center**: A guide that marks the horizontal center of the view.
- **trailing**: A guide that marks the trailing edge of the view.
- **listRowSeparatorLeading**: A guide marking the leading edge of a `List` row separator.

