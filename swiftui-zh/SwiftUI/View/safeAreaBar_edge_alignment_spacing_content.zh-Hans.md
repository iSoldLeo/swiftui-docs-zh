--- 来源：https://developer.apple.com/documentation/SwiftUI/View/safeAreaBar(edge:alignment:spacing:content:)

抓取时间：2025-12-02T17:25:14Z

---

# safeAreaBar(edge:alignment:spacing:content:)

**实例方法**

将指定内容显示为修改后的视图旁边的自定义栏。

## 声明

```swift
nonisolated func safeAreaBar(edge: HorizontalEdge, alignment: VerticalAlignment = .center, spacing: CGFloat? = nil, @ViewBuilder content: () -> some View) -> some View

```

## 参数

- **edge**：`content` 所在视图的水平边缘。

- **alignment**：用于垂直定位 `content` 的对齐参考线。

- **spacing**：两个视图之间的额外距离，如果设置为 nil 则使用默认间距。

- **content**：视图构建器函数，提供要显示为自定义栏的视图。

## 返回值

一个新视图，显示在修改后的视图旁边，`content` 通过水平内移修改后的视图，为 `content` 视图腾出空间，并调整安全区域和滚动边缘效果以匹配。

## 说明

与 [doc://com.apple.SwiftUI/documentation/SwiftUI/View/safeAreaInset(edge:alignment:spacing:content:)-6gwby] 修改器类似，`content` 视图锚定到父视图的指定水平边缘，其宽度会内移安全区域。

此外，它还会扩展受内移安全区域影响的任何滚动视图的边缘效果。

## 配置滚动边缘效果

- **scrollEdgeEffectStyle(_:for:)**：配置此层级结构中滚动视图的滚动边缘效果样式。

- **scrollEdgeEffectHidden(_:for:)**：隐藏此层级结构中滚动视图的所有滚动边缘效果。

- **ScrollEdgeEffectStyle**：定义滚动视图的凹槽样式的结构体。


---
source: https://developer.apple.com/documentation/SwiftUI/View/safeAreaBar(edge:alignment:spacing:content:)
crawled: 2025-12-02T17:25:14Z
---

# safeAreaBar(edge:alignment:spacing:content:)

**Instance Method**

Shows the specified content as a custom bar beside the modified view.

## Declaration

```swift
nonisolated func safeAreaBar(edge: HorizontalEdge, alignment: VerticalAlignment = .center, spacing: CGFloat? = nil, @ViewBuilder content: () -> some View) -> some View

```

## Parameters

- **edge**: The horizontal edge of the view on which `content` is placed.
- **alignment**: The alignment guide used to position `content` vertically.
- **spacing**: Extra distance placed between the two views, or nil to use the default amount of spacing.
- **content**: A view builder function providing the view to display as a custom bar.

## Return Value

A new view that displays `content` beside the modified view, making space for the `content` view by horizontally insetting the modified view, adjusting the safe area and scroll edge effects to match.

## Discussion

Similar to the [doc://com.apple.SwiftUI/documentation/SwiftUI/View/safeAreaInset(edge:alignment:spacing:content:)-6gwby] modifier, the `content` view is anchored to the specified horizontal edge of the parent view and its width insets the safe area.

Additionally, it extends the edge effect of any scroll views affected by the inset safe area.

## Configuring scroll edge effects

- **scrollEdgeEffectStyle(_:for:)**: Configures the scroll edge effect style for scroll views within this hierarchy.
- **scrollEdgeEffectHidden(_:for:)**: Hides any scroll edge effects for scroll views within this hierarchy.
- **ScrollEdgeEffectStyle**: A structure that defines the style of pocket a scroll view will have.

