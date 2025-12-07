--- 来源：https://developer.apple.com/documentation/SwiftUI/View/listSectionSpacing(_:)

抓取时间：2025-12-02T17:39:30Z

---

# listSectionSpacing(_:)

**实例方法**

设置列表（[List](../List.zh-Hans.md)）中相邻部分之间的间距为自定义值。

## 声明

```swift
nonisolated func listSectionSpacing(_ spacing: CGFloat) -> some View

```

## 参数

- **spacing**：要应用的间距量。

## 讨论

以下示例创建了一个 [List](../List.zh-Hans.md)，各部分之间的间距为 5 磅：

```swift
List {
    Section("Colors") {
        Text("Blue")
        Text("Red")
    }

    Section("Shapes") {
        Text("Square")
        Text("Circle")
    }
}
.listSectionSpacing(5.0)
```

也可以在单个 [Section](../Section.zh-Hans.md) 上指定间距，如下例所示：

```swift
Section("Borders") {
    Text("Dashed")
    Text("Solid")
}
.listSectionSpacing(10.0)
```

如果相邻部分应用了不同的间距，则每个部分都会应用其自身间距的一半，分别位于其上方和下方。未显式设置间距的部分将应用其相邻部分的间距。

```swift
List {
    Section("Colors") {
        Text("Blue")
        Text("Red")
    }

    Section("Borders") {
        Text("Dashed")
        Text("Solid")
    }
    .listSectionSpacing(10.0)

    Section("Shapes") {
        Text("Square")
        Text("Circle")
    }
    .listSectionSpacing(100.0)
}
```

在上面的示例中，“颜色”和“边框”部分之间的间距为 10 磅，“边框”和“形状”部分之间的间距为 55 磅。

[List](../List.zh-Hans.md) 中各部分应用的间距会覆盖 [List](../List.zh-Hans.md) 整体应用的间距。

## 配置列表布局

- **listRowInsets(_:)**：设置列表行的内边距。

- **defaultMinListRowHeight**：设置列表行的默认最小高度。

- **defaultMinListHeaderHeight**：设置列表标题的默认最小高度。

- **listRowSpacing(_:)**：设置列表中相邻两行之间的垂直间距。

- **ListSectionSpacing**：设置列表中相邻两个部分之间的间距选项。

- **listSectionMargins(_:_:)**：设置特定边缘的部分边距。


---
source: https://developer.apple.com/documentation/SwiftUI/View/listSectionSpacing(_:)
crawled: 2025-12-02T17:39:30Z
---

# listSectionSpacing(_:)

**Instance Method**

Sets the spacing between adjacent sections in a [List](../List.zh-Hans.md) to a custom value.

## Declaration

```swift
nonisolated func listSectionSpacing(_ spacing: CGFloat) -> some View

```

## Parameters

- **spacing**: The amount of spacing to apply.

## Discussion

The following example creates a [List](../List.zh-Hans.md) with 5 pts of spacing between sections:

```swift
List {
    Section("Colors") {
        Text("Blue")
        Text("Red")
    }

    Section("Shapes") {
        Text("Square")
        Text("Circle")
    }
}
.listSectionSpacing(5.0)
```

Spacing can also be specified on an individual [Section](../Section.zh-Hans.md), as in this example:

```swift
Section("Borders") {
    Text("Dashed")
    Text("Solid")
}
.listSectionSpacing(10.0)
```

If adjacent sections have different spacing applied, each section applies half its spacing above and below. Sections without explicit spacing apply the spacing of their adjacent sections.

```swift
List {
    Section("Colors") {
        Text("Blue")
        Text("Red")
    }

    Section("Borders") {
        Text("Dashed")
        Text("Solid")
    }
    .listSectionSpacing(10.0)

    Section("Shapes") {
        Text("Square")
        Text("Circle")
    }
    .listSectionSpacing(100.0)
}
```

In the above example, the “Colors” and “Borders” section are separated by 10 pts of spacing, and the “Borders” and “Shapes” section are separated by 55 pts of spacing.

Spacing applied on sections in the [List](../List.zh-Hans.md) overrides spacing applied on the [List](../List.zh-Hans.md) as a whole.

## Configuring a list’s layout

- **listRowInsets(_:)**: Applies an inset to the rows in a list.
- **defaultMinListRowHeight**: The default minimum height of rows in a list.
- **defaultMinListHeaderHeight**: The default minimum height of a header in a list.
- **listRowSpacing(_:)**: Sets the vertical spacing between two adjacent rows in a List.
- **ListSectionSpacing**: The spacing options between two adjacent sections in a list.
- **listSectionMargins(_:_:)**: Set the section margins for the specific edges.

