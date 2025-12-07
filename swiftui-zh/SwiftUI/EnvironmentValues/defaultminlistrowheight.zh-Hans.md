---
来源： https://developer.apple.com/documentation/swiftui/environmentvalues/defaultminlistrowheight
抓取时间： 2025-12-04T13:10:36Z
---

# defaultMinListRowHeight

**实例属性**

列表中行的默认最小高度。

## 声明

```swift
var defaultMinListRowHeight: CGFloat { get set }
```

## 讨论

列表行的高度以该默认值为界，否则将由行内容和行嵌入部分的高度决定。

## 配置列表布局

- **listRowInsets(_:)**：为列表中的行应用嵌入。
- **defaultMinListHeaderHeight**：列表中标题的默认最小高度。
- **listRowSpacing(_:)**：设置列表中相邻两行之间的垂直间距。
- **listSectionSpacing(_:)**：设置列表中相邻两行之间的垂直间距：将[List](../List.zh-Hans.md) 中相邻部分的间距设置为自定义值。
- **ListSectionSpacing**：列表中两个相邻部分之间的间距选项。
- **listSectionMargins(_:_:)**：设置特定边缘的部分边距。


---
source: https://developer.apple.com/documentation/swiftui/environmentvalues/defaultminlistrowheight
crawled: 2025-12-04T13:10:36Z
---

# defaultMinListRowHeight

**Instance Property**

The default minimum height of rows in a list.

## Declaration

```swift
var defaultMinListRowHeight: CGFloat { get set }
```

## Discussion

The height of list rows is bounded below by this default value, and is otherwise determined by the height of the row’s content and the row insets.

## Configuring a list’s layout

- **listRowInsets(_:)**: Applies an inset to the rows in a list.
- **defaultMinListHeaderHeight**: The default minimum height of a header in a list.
- **listRowSpacing(_:)**: Sets the vertical spacing between two adjacent rows in a List.
- **listSectionSpacing(_:)**: Sets the spacing between adjacent sections in a [List](../List.zh-Hans.md) to a custom value.
- **ListSectionSpacing**: The spacing options between two adjacent sections in a list.
- **listSectionMargins(_:_:)**: Set the section margins for the specific edges.

