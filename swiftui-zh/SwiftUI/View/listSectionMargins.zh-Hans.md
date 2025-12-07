--- 来源：https://developer.apple.com/documentation/SwiftUI/View/listSectionMargins(_:_:)

抓取时间：2025-11-30T21:09:16Z

---

# listSectionMargins(_:_:)

**实例方法**

设置指定边的分区边距。

## 声明

```swift
nonisolated func listSectionMargins(_ edges: Edge.Set = .all, _ length: CGFloat?) -> some View

```

## 参数

- **edges**：此视图中要为分区添加边距的边集。默认值为 [all](../Edge/Set/all.zh-Hans.md)。

- **length**：指定边上分区的边距值（以点为单位）。

## 返回值

返回一个视图，其中列表分区的边距已设置为指定边距值。

## 讨论

在列表节上使用此修饰符可自定义其边距。要设置边距，请指定要设置边距的边缘，方法是指定 [Set](../Edge/Set.zh-Hans.md) 中的单个值，或指定包含边缘值的 [doc://com.apple.documentation/documentation/Swift/OptionSet]。其他边缘的边距保持不变。

默认节边距基于列表样式、列表节间距和列表内容边距。使用此修饰符将完全覆盖这些默认值。

对于带有页眉或页脚的节，节边距将应用于这些页眉或页脚周围。

## 配置列表布局

- **listRowInsets(_:)**：为列表中的行应用内边距。

- **defaultMinListRowHeight**：列表中行的默认最小高度。

- **defaultMinListHeaderHeight**：列表中标题的默认最小高度。

- **listRowSpacing(_:)**：设置列表中相邻两行之间的垂直间距。

- **listSectionSpacing(_:)**：将 [List](../List.zh-Hans.md) 中相邻节之间的间距设置为自定义值。

- **ListSectionSpacing**：列表中相邻节之间的间距选项。


---
source: https://developer.apple.com/documentation/SwiftUI/View/listSectionMargins(_:_:)
crawled: 2025-11-30T21:09:16Z
---

# listSectionMargins(_:_:)

**Instance Method**

Set the section margins for the specific edges.

## Declaration

```swift
nonisolated func listSectionMargins(_ edges: Edge.Set = .all, _ length: CGFloat?) -> some View

```

## Parameters

- **edges**: The set of edges to pad for sections in this view. The default is [all](../Edge/Set/all.zh-Hans.md).
- **length**: An amount, given in points, to pad section on the specified edges.

## Return Value

A view in which the margins of list sections are set to the specified amount on the specified edges.

## Discussion

Use this modifier on a list section to set customize its margins. Indicate the edges to set the margin of by naming either a single value from  [Set](../Edge/Set.zh-Hans.md), or by specifying an [doc://com.apple.documentation/documentation/Swift/OptionSet] that contains edge values. Margins for the other edges remain unchanged.

The default section margins are based on the list style, list section spacing and content margins of the list. Using this modifier overrides these default values completely.

For sections that have headers or footers, the section margins are applied around these.

## Configuring a list’s layout

- **listRowInsets(_:)**: Applies an inset to the rows in a list.
- **defaultMinListRowHeight**: The default minimum height of rows in a list.
- **defaultMinListHeaderHeight**: The default minimum height of a header in a list.
- **listRowSpacing(_:)**: Sets the vertical spacing between two adjacent rows in a List.
- **listSectionSpacing(_:)**: Sets the spacing between adjacent sections in a [List](../List.zh-Hans.md) to a custom value.
- **ListSectionSpacing**: The spacing options between two adjacent sections in a list.

