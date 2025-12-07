--- 来源：https://developer.apple.com/documentation/SwiftUI/View/listSectionSeparator(_:edges:)

抓取时间：2025-11-30T21:24:43Z

---

# listSectionSeparator(_:edges:)

**实例方法**

设置是否隐藏列表部分的分隔符。

## 声明

```swift
nonisolated func listSectionSeparator(_ visibility: Visibility, edges: VerticalEdge.Set = .all) -> some View

```

## 参数

- **visibility**：此部分分隔符的可见性。

- **edges**：应用此首选项的行边缘集合。列表样式可能已经决定不显示某些边缘的分隔符。默认值为 [all](../VerticalEdge/Set/all.zh-Hans.md)。

## 说明

分隔符可以显示在部分的上方和下方。您可以指定此首选项应应用于哪个边缘。

此修饰符表示对包含项 [List](../List.zh-Hans.md) 的偏好。列表样式最终决定分隔符的可见性。

以下示例显示了一个简单的分组列表，其底部节分隔符已隐藏：

```swift
List {
    ForEach(garage) { garage in
        Section(header: Text(garage.location)) {
            ForEach(garage.cars) { car in
                Text(car.model)
                    .listRowSeparatorTint(car.brandColor)
            }
        }
        .listSectionSeparator(.hidden, edges: .bottom)
    }
}
.listStyle(.grouped)
```

要更改行分隔符的可见性和色调颜色，请使用 [listRowSeparator(_:edges:)](listRowSeparator___edges.zh-Hans.md) 和 [listRowSeparatorTint(_:edges:)](listRowSeparatorTint___edges.zh-Hans.md)。要设置节分隔符的色调颜色，请使用 [listSectionSeparatorTint(_:edges:)](listSectionSeparatorTint___edges.zh-Hans.md)。

## 配置分隔符

- **listRowSeparatorTint(_:edges:)**：设置与行关联的色调颜色。

- **listSectionSeparatorTint(_:edges:)**：设置与节关联的色调颜色。

- **listRowSeparator(_:edges:)**：设置与此特定行关联的分隔符的显示模式。


---
source: https://developer.apple.com/documentation/SwiftUI/View/listSectionSeparator(_:edges:)
crawled: 2025-11-30T21:24:43Z
---

# listSectionSeparator(_:edges:)

**Instance Method**

Sets whether to hide the separator associated with a list section.

## Declaration

```swift
nonisolated func listSectionSeparator(_ visibility: Visibility, edges: VerticalEdge.Set = .all) -> some View

```

## Parameters

- **visibility**: The visibility of this section’s separators.
- **edges**: The set of row edges for which the preference applies. The list style might already decide to not display separators for some edges. The default is [all](../VerticalEdge/Set/all.zh-Hans.md).

## Discussion

Separators can be presented above and below a section. You can specify to which edge this preference should apply.

This modifier expresses a preference to the containing [List](../List.zh-Hans.md). The list style is the final arbiter of the separator visibility.

The following example shows a simple grouped list whose bottom sections separator are hidden:

```swift
List {
    ForEach(garage) { garage in
        Section(header: Text(garage.location)) {
            ForEach(garage.cars) { car in
                Text(car.model)
                    .listRowSeparatorTint(car.brandColor)
            }
        }
        .listSectionSeparator(.hidden, edges: .bottom)
    }
}
.listStyle(.grouped)
```

To change the visibility and tint color for a row separator, use [listRowSeparator(_:edges:)](listRowSeparator___edges.zh-Hans.md) and [listRowSeparatorTint(_:edges:)](listRowSeparatorTint___edges.zh-Hans.md). To set the tint color for a section separator, use [listSectionSeparatorTint(_:edges:)](listSectionSeparatorTint___edges.zh-Hans.md).

## Configuring separators

- **listRowSeparatorTint(_:edges:)**: Sets the tint color associated with a row.
- **listSectionSeparatorTint(_:edges:)**: Sets the tint color associated with a section.
- **listRowSeparator(_:edges:)**: Sets the display mode for the separator associated with this specific row.

