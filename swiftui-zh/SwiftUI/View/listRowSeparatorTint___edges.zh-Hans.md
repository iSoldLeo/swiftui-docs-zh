--- 来源：https://developer.apple.com/documentation/SwiftUI/View/listRowSeparatorTint(_:edges:)

抓取时间：2025-11-30T20:49:58Z

---

# listRowSeparatorTint(_:edges:)

**实例方法**

设置与行关联的着色颜色。

## 声明

```swift
nonisolated func listRowSeparatorTint(_ color: Color?, edges: VerticalEdge.Set = .all) -> some View

```

## 参数

- **color**：用于着色行分隔符的颜色，或 `nil`：使用当前列表样式的默认颜色。

- **edges**：应用着色的行边缘集合。列表样式可能会决定不显示某些分隔符，通常是顶部边缘。默认值为 [all](../VerticalEdge/Set/all.zh-Hans.md)。

## 讨论

分隔符可以显示在行的上方和下方。您可以指定此首选项应用于哪一边缘。

此修饰符表示对包含 [List](../List.zh-Hans.md) 的偏好。列表样式是分隔符颜色的最终决定因素。

以下示例显示了一个简单的分组列表，其行分隔符的颜色根据行特定数据而变化：

```swift
List {
    ForEach(garage.cars) { car in
        Text(car.model)
            .listRowSeparatorTint(car.brandColor)
    }
}
.listStyle(.grouped)
```

要隐藏行分隔符，请使用 [listRowSeparator(_:edges:)](listRowSeparator___edges.zh-Hans.md)。要隐藏或更改节分隔符的颜色，请使用 [listSectionSeparator(_:edges:)](listSectionSeparator___edges.zh-Hans.md) 和 [listSectionSeparatorTint(_:edges:)](listSectionSeparatorTint___edges.zh-Hans.md)。

## 配置分隔符

- **listSectionSeparatorTint(_:edges:)**：设置与节关联的颜色。

- **listRowSeparator(_:edges:)**：设置与此行关联的分隔符的显示模式。

- **listSectionSeparator(_:edges:)**：设置是否隐藏与列表部分关联的分隔符。


---
source: https://developer.apple.com/documentation/SwiftUI/View/listRowSeparatorTint(_:edges:)
crawled: 2025-11-30T20:49:58Z
---

# listRowSeparatorTint(_:edges:)

**Instance Method**

Sets the tint color associated with a row.

## Declaration

```swift
nonisolated func listRowSeparatorTint(_ color: Color?, edges: VerticalEdge.Set = .all) -> some View

```

## Parameters

- **color**: The color to use to tint the row separators, or `nil` to use the default color for the current list style.
- **edges**: The set of row edges for which the tint applies. The list style might decide to not display certain separators, typically the top edge. The default is [all](../VerticalEdge/Set/all.zh-Hans.md).

## Discussion

Separators can be presented above and below a row. You can specify to which edge this preference should apply.

This modifier expresses a preference to the containing [List](../List.zh-Hans.md). The list style is the final arbiter for the separator tint.

The following example shows a simple grouped list whose row separators are tinted based on row-specific data:

```swift
List {
    ForEach(garage.cars) { car in
        Text(car.model)
            .listRowSeparatorTint(car.brandColor)
    }
}
.listStyle(.grouped)
```

To hide a row separators, use [listRowSeparator(_:edges:)](listRowSeparator___edges.zh-Hans.md). To hide or change the tint color for a section separator, use [listSectionSeparator(_:edges:)](listSectionSeparator___edges.zh-Hans.md) and [listSectionSeparatorTint(_:edges:)](listSectionSeparatorTint___edges.zh-Hans.md).

## Configuring separators

- **listSectionSeparatorTint(_:edges:)**: Sets the tint color associated with a section.
- **listRowSeparator(_:edges:)**: Sets the display mode for the separator associated with this specific row.
- **listSectionSeparator(_:edges:)**: Sets whether to hide the separator associated with a list section.

