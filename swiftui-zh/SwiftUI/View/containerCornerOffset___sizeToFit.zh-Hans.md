--- 来源：https://developer.apple.com/documentation/SwiftUI/View/containerCornerOffset(_:sizeToFit:)

抓取时间：2025-12-02T17:23:21Z

---

# containerCornerOffset(_:sizeToFit:)

**实例方法**

调整视图的布局，使其避开容器视图在指定边上的角内缩。

## 声明

```swift
nonisolated func containerCornerOffset(_ edges: Edge.Set, sizeToFit: Bool = false) -> some View

```

## 参数

- **edges**：容器视图应从中添加角内缩的边的集合。

- **sizeToFit**：一个标志，指示当此视图偏离角内缩时，其大小是应尝试适应视图的剩余空间，还是填充其原始大小。

## 讨论

当您希望视图布局能够自动调整，以避开容器视图的某些边角时，请使用此修饰符。边角可能包含系统 UI 元素以及窗口和演示文稿的圆角半径。如果指定了特定边，则视图将定位以避开该边角的边角。当多个边角在同一轴上重叠时，视图将定位在重叠边角较大的区域之外。

```swift
DrawingCanvasView(canvas: $canvas)
    .ignoresSafeArea()
    .overlay(alignment: .topLeading) {
        DrawingToolPaletteView(tool: $selectedTool)
            .containerCornerOffset(.horizontal)
    }
```

此修饰符提供了一个 `sizeToFit` 参数，用于指示视图在偏离边角后应如何调整大小。默认情况下，使用 `false` 参数，此时内容的大小将保持不变，仅视图内容的位置会发生偏移。当 `true` 时，内容将尝试根据原始视图剩余尺寸减去重叠角点内边距后的尺寸来调整自身大小。


---
source: https://developer.apple.com/documentation/SwiftUI/View/containerCornerOffset(_:sizeToFit:)
crawled: 2025-12-02T17:23:21Z
---

# containerCornerOffset(_:sizeToFit:)

**Instance Method**

Adjusts the view’s layout to avoid the container view’s corner insets for the specified edges.

## Declaration

```swift
nonisolated func containerCornerOffset(_ edges: Edge.Set, sizeToFit: Bool = false) -> some View

```

## Parameters

- **edges**: The set of edges which the container view should add corner insets from.
- **sizeToFit**: A flag indicating when this view is offset off a corner inset whether its size should attempt to fit into its remaining space of the view or fill its original size.

## Discussion

Use this modifier when you would like the view’s layout to adapt to avoid the container view’s corner insets for a set of edges. Corner insets may include pieces of system UI as well as the corner radii for windows and presentations. When a specific edge is provided the view is positioned to avoid insets from only the corners of that edge. When multiple corner edges overlap in the same axis the view will be positioned off the larger overlapping inset.

```swift
DrawingCanvasView(canvas: $canvas)
    .ignoresSafeArea()
    .overlay(alignment: .topLeading) {
        DrawingToolPaletteView(tool: $selectedTool)
            .containerCornerOffset(.horizontal)
    }
```

The modifier provides a `sizeToFit` parameter to indicate how the view should be sized when it has been offset from a corner inset. By default, `false` is provided, and the content’s size will be unchanged, only the position of the view’s content will be offset. When `true`, the content will attempt to size itself with a proposal using the remaining size of the original view subtracted from the overlapping corner insets.

