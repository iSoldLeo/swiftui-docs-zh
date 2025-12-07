--- 来源：https://developer.apple.com/documentation/SwiftUI/View/listRowSeparator(_:edges:)

抓取时间：2025-12-02T17:39:36Z

---

# listRowSeparator(_:edges:)

**实例方法**

设置与此特定行关联的分隔符的显示模式。

## 声明

```swift
nonisolated func listRowSeparator(_ visibility: Visibility, edges: VerticalEdge.Set = .all) -> some View

```

## 参数

- **visibility**：此行分隔符的可见性。

- **edges**：应用此首选项的行边缘集合。列表样式可能已经决定不显示某些边缘（通常是顶部边缘）的分隔符。默认值为 [all](../VerticalEdge/Set/all.zh-Hans.md)。

## 讨论

分隔符可以显示在行的上方和下方。您可以指定此首选项应用于哪个边。

此修饰符表示对包含元素 [List](../List.zh-Hans.md) 的首选项。列表样式是分隔符可见性的最终决定因素。

以下示例显示了一个简单的分组列表，其行分隔符已隐藏：

```swift
List {
    ForEach(garage.cars) { car in
        Text(car.model)
            .listRowSeparator(.hidden)
    }
}
.listStyle(.grouped)
```

要更改行分隔符的颜色，请使用 [listRowSeparatorTint(_:edges:)](listRowSeparatorTint___edges.zh-Hans.md)。要隐藏或更改节分隔符的色调颜色，请使用 [listSectionSeparator(_:edges:)](listSectionSeparator___edges.zh-Hans.md) 和 [listSectionSeparatorTint(_:edges:)](listSectionSeparatorTint___edges.zh-Hans.md)。

## 配置分隔符

- **listRowSeparatorTint(_:edges:)**：设置与行关联的色调颜色。

- **listSectionSeparatorTint(_:edges:)**：设置与节关联的色调颜色。

- **listSectionSeparator(_:edges:)**：设置是否隐藏列表部分的分隔符。


---
source: https://developer.apple.com/documentation/SwiftUI/View/listRowSeparator(_:edges:)
crawled: 2025-12-02T17:39:36Z
---

# listRowSeparator(_:edges:)

**Instance Method**

Sets the display mode for the separator associated with this specific row.

## Declaration

```swift
nonisolated func listRowSeparator(_ visibility: Visibility, edges: VerticalEdge.Set = .all) -> some View

```

## Parameters

- **visibility**: The visibility of this row’s separators.
- **edges**: The set of row edges for which this preference applies. The list style might already decide to not display separators for some edges, typically the top edge. The default is [all](../VerticalEdge/Set/all.zh-Hans.md).

## Discussion

Separators can be presented above and below a row. You can specify to which edge this preference should apply.

This modifier expresses a preference to the containing [List](../List.zh-Hans.md). The list style is the final arbiter of the separator visibility.

The following example shows a simple grouped list whose row separators are hidden:

```swift
List {
    ForEach(garage.cars) { car in
        Text(car.model)
            .listRowSeparator(.hidden)
    }
}
.listStyle(.grouped)
```

To change the color of a row separators, use [listRowSeparatorTint(_:edges:)](listRowSeparatorTint___edges.zh-Hans.md). To hide or change the tint color for a section separators, use [listSectionSeparator(_:edges:)](listSectionSeparator___edges.zh-Hans.md) and [listSectionSeparatorTint(_:edges:)](listSectionSeparatorTint___edges.zh-Hans.md).

## Configuring separators

- **listRowSeparatorTint(_:edges:)**: Sets the tint color associated with a row.
- **listSectionSeparatorTint(_:edges:)**: Sets the tint color associated with a section.
- **listSectionSeparator(_:edges:)**: Sets whether to hide the separator associated with a list section.

