---
来源： https://developer.apple.com/documentation/swiftui/environmentvalues/defaultminlistheaderheight
抓取时间： 2025-12-04T13:10:35Z
---

# defaultMinListHeaderHeight

**实例属性**

列表中标题的默认最小高度。

## 声明

```swift
var defaultMinListHeaderHeight: CGFloat? { get set }
```

## 讨论

当该值为`nil` 时，系统会选择适当的高度。默认值为 `nil`。

## 配置列表布局

- **listRowInsets(_:)**：对列表中的行应用嵌入。
- **defaultMinListRowHeight**：列表中行的默认最小高度。
- **listRowSpacing(_:)**：设置列表中相邻两行之间的垂直间距。
- **listSectionSpacing(_:)**：设置列表中相邻两行之间的垂直间距：将[List](../List.zh-Hans.md) 中相邻部分的间距设置为自定义值。
- **ListSectionSpacing**：列表中两个相邻部分之间的间距选项。
- **listSectionMargins(_:_:)**：设置特定边缘的部分边距。


---
source: https://developer.apple.com/documentation/swiftui/environmentvalues/defaultminlistheaderheight
crawled: 2025-12-04T13:10:35Z
---

# defaultMinListHeaderHeight

**Instance Property**

The default minimum height of a header in a list.

## Declaration

```swift
var defaultMinListHeaderHeight: CGFloat? { get set }
```

## Discussion

When this value is `nil`, the system chooses the appropriate height. The default is `nil`.

## Configuring a list’s layout

- **listRowInsets(_:)**: Applies an inset to the rows in a list.
- **defaultMinListRowHeight**: The default minimum height of rows in a list.
- **listRowSpacing(_:)**: Sets the vertical spacing between two adjacent rows in a List.
- **listSectionSpacing(_:)**: Sets the spacing between adjacent sections in a [List](../List.zh-Hans.md) to a custom value.
- **ListSectionSpacing**: The spacing options between two adjacent sections in a list.
- **listSectionMargins(_:_:)**: Set the section margins for the specific edges.

