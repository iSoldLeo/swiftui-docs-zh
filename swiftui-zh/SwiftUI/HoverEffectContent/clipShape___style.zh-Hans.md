--- 来源：https://developer.apple.com/documentation/SwiftUI/HoverEffectContent/clipShape(_:style:)

抓取时间：2025-12-03T06:45:51Z

---

# clipShape(_:style:)

**实例方法**

为视图设置裁剪形状。

## 声明

```swift
func clipShape<S>(_ shape: S, style: FillStyle = FillStyle()) -> some HoverEffectContent where S : Shape

```

## 参数

- **shape**：用于视图的裁剪形状。`shape` 会填充视图的框架，同时保持其宽高比。

- **style**：栅格化 `shape` 时使用的填充样式。

## 返回值

设置视图裁剪形状的效果。

## 讨论

使用 `clipShape(_:style:)` 将视图的渲染输出裁剪到指定的形状。通过应用裁剪形状，您可以保留视图中被该形状覆盖的部分，同时去除视图的其他部分。裁剪形状本身是不可见的。


---
source: https://developer.apple.com/documentation/SwiftUI/HoverEffectContent/clipShape(_:style:)
crawled: 2025-12-03T06:45:51Z
---

# clipShape(_:style:)

**Instance Method**

Sets a clipping shape for the view.

## Declaration

```swift
func clipShape<S>(_ shape: S, style: FillStyle = FillStyle()) -> some HoverEffectContent where S : Shape

```

## Parameters

- **shape**: The clipping shape to use for the view. The `shape` fills the view’s frame, while maintaining its aspect ratio.
- **style**: The fill style to use when rasterizing `shape`.

## Return Value

An effect that sets the clip shape of a view.

## Discussion

Use `clipShape(_:style:)` to clip the view’s rendered output to the provided shape. By applying a clipping shape, you preserve the parts of the view covered by the shape, while eliminating other parts of the view. The clipping shape itself isn’t visible.

