--- 来源：https://developer.apple.com/documentation/SwiftUI/View/listRowSpacing(_:)

抓取时间：2025-11-30T21:24:34Z

---

# listRowSpacing(_:)

**实例方法**

设置列表中相邻两行之间的垂直间距。

## 声明

```swift
nonisolated func listRowSpacing(_ spacing: CGFloat?) -> some View

```

## 参数

- **spacing**：要使用的间距值。值为 `nil` 时使用默认间距。

## 说明

以下示例创建一个列表，每行之间的间距为 10 磅：

```swift
List {
    Text("Blue")
    Text("Red")
}
.listRowSpacing(10.0)
```

## 配置列表布局

- **listRowInsets(_:)**：为列表中的行应用内边距。

- **defaultMinListRowHeight**：列表中行的默认最小高度。

- **defaultMinListHeaderHeight**：列表中标题的默认最小高度。

- **listSectionSpacing(_:)**：将 [List](../List.zh-Hans.md) 中相邻部分之间的间距设置为自定义值。

- **ListSectionSpacing**：列表中两个相邻部分之间的间距选项。

- **listSectionMargins(_:_:)**：设置特定边缘的节边距。


---
source: https://developer.apple.com/documentation/SwiftUI/View/listRowSpacing(_:)
crawled: 2025-11-30T21:24:34Z
---

# listRowSpacing(_:)

**Instance Method**

Sets the vertical spacing between two adjacent rows in a List.

## Declaration

```swift
nonisolated func listRowSpacing(_ spacing: CGFloat?) -> some View

```

## Parameters

- **spacing**: The spacing value to use. A value of `nil` uses the default spacing.

## Discussion

The following example creates a List with 10 pts of spacing between each row:

```swift
List {
    Text("Blue")
    Text("Red")
}
.listRowSpacing(10.0)
```

## Configuring a list’s layout

- **listRowInsets(_:)**: Applies an inset to the rows in a list.
- **defaultMinListRowHeight**: The default minimum height of rows in a list.
- **defaultMinListHeaderHeight**: The default minimum height of a header in a list.
- **listSectionSpacing(_:)**: Sets the spacing between adjacent sections in a [List](../List.zh-Hans.md) to a custom value.
- **ListSectionSpacing**: The spacing options between two adjacent sections in a list.
- **listSectionMargins(_:_:)**: Set the section margins for the specific edges.

