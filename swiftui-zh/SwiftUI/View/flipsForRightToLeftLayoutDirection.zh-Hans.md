--- 来源：https://developer.apple.com/documentation/SwiftUI/View/flipsForRightToLeftLayoutDirection(_:)

抓取时间：2025-11-30T21:20:14Z

---

# flipsForRightToLeftLayoutDirection(_:)

**实例方法**

设置当布局方向为从右到左时，此视图是否水平镜像其内容。

## 声明

```swift
nonisolated func flipsForRightToLeftLayoutDirection(_ enabled: Bool) -> some View

```

## 参数

- **enabled**：一个布尔值，指示当布局方向为从右到左时，此视图的内容是否应该水平翻转。默认情况下，视图会在从右到左的上下文中自动调整其布局，无需镜像。

## 返回值

一个在布局方向为从右到左时有条件地水平镜像其内容的视图。

## 讨论

当需要在从右到左的布局中显示视图内容时，使用 `flipsForRightToLeftLayoutDirection(_:)` 来水平镜像视图内容。

要覆盖特定视图的布局方向，请使用 [environment(_:_:)](environment.zh-Hans.md) 视图修饰符显式覆盖该视图的 [layoutDirection](../EnvironmentValues/layoutDirection.zh-Hans.md) 环境值。

## 管理文本布局

- **truncationMode(_:)**：设置文本行过长而无法容纳在可用空间中的截断模式。

- **truncationMode**：指示布局如何截断最后一行文本以适应可用空间的值。

- **allowsTightening(_:)**：设置此视图中的文本是否可以在必要时压缩字符间距以适应一行。

- **allowsTightening**：一个布尔值，指示是否应缩小字符间距以使文本适应可用空间。

- **minimumScaleFactor(_:)**：设置此视图中文本缩小以适应可用空间的最小比例。

- **minimumScaleFactor**：缩小字体大小以适应可用空间的最小允许比例。

- **baselineOffset(_:)**：设置此视图中文本相对于其基线的垂直偏移量。

- **kerning(_:)**：设置此视图中文本的字符间距（或字距调整）。

- **tracking(_:)**：设置此视图中文本的字距调整。

- **TextAlignment**：文本沿水平轴的对齐位置。


---
source: https://developer.apple.com/documentation/SwiftUI/View/flipsForRightToLeftLayoutDirection(_:)
crawled: 2025-11-30T21:20:14Z
---

# flipsForRightToLeftLayoutDirection(_:)

**Instance Method**

Sets whether this view mirrors its contents horizontally when the layout direction is right-to-left.

## Declaration

```swift
nonisolated func flipsForRightToLeftLayoutDirection(_ enabled: Bool) -> some View

```

## Parameters

- **enabled**: A Boolean value that indicates whether this view should have its content flipped horizontally when the layout direction is right-to-left. By default, views will adjust their layouts automatically in a right-to-left context and do not need to be mirrored.

## Return Value

A view that conditionally mirrors its contents horizontally when the layout direction is right-to-left.

## Discussion

Use `flipsForRightToLeftLayoutDirection(_:)` when you need the system to horizontally mirror the contents of the view when presented in a right-to-left layout.

To override the layout direction for a specific view, use the [environment(_:_:)](environment.zh-Hans.md) view modifier to explicitly override the [layoutDirection](../EnvironmentValues/layoutDirection.zh-Hans.md) environment value for the view.

## Managing text layout

- **truncationMode(_:)**: Sets the truncation mode for lines of text that are too long to fit in the available space.
- **truncationMode**: A value that indicates how the layout truncates the last line of text to fit into the available space.
- **allowsTightening(_:)**: Sets whether text in this view can compress the space between characters when necessary to fit text in a line.
- **allowsTightening**: A Boolean value that indicates whether inter-character spacing should tighten to fit the text into the available space.
- **minimumScaleFactor(_:)**: Sets the minimum amount that text in this view scales down to fit in the available space.
- **minimumScaleFactor**: The minimum permissible proportion to shrink the font size to fit the text into the available space.
- **baselineOffset(_:)**: Sets the vertical offset for the text relative to its baseline in this view.
- **kerning(_:)**: Sets the spacing, or kerning, between characters for the text in this view.
- **tracking(_:)**: Sets the tracking for the text in this view.
- **TextAlignment**: An alignment position for text along the horizontal axis.

