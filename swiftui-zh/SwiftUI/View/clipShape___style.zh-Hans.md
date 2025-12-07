--- 来源：https://developer.apple.com/documentation/SwiftUI/View/clipShape(_:style:)

抓取时间：2025-11-30T21:22:28Z

---

# clipShape(_:style:)

**实例方法**

为此视图设置裁剪形状。

## 声明

```swift
nonisolated func clipShape<S>(_ shape: S, style: FillStyle = FillStyle()) -> some View where S : Shape

```

## 参数

- **shape**：用于此视图的裁剪形状。`shape` 会填充视图的框架，同时保持其宽高比。

- **style**：栅格化 `shape` 时使用的填充样式。

## 返回值

返回一个视图，该视图使用 `style` 定义形状的栅格化，并将当前视图裁剪到 `shape`。

## 说明

使用 `clipShape(_:style:)` 将视图裁剪到指定的形状。通过将裁剪形状应用于视图，您可以保留被该形状覆盖的视图部分，同时消除视图的其他部分。裁剪形状本身是不可见的。

例如，以下代码将圆形裁剪形状应用于 `Text` 视图：

```swift
Text("Clipped text in a circle")
    .frame(width: 175, height: 100)
    .foregroundColor(Color.white)
    .background(Color.black)
    .clipShape(Circle())
```

生成的视图仅显示位于圆内边界内的文本部分。

## 遮罩和裁剪

- **mask(alignment:_:)**：使用给定视图的 Alpha 通道遮罩当前视图。

- **clipped(antialiased:)**：将此视图裁剪到其边界矩形框内。


---
source: https://developer.apple.com/documentation/SwiftUI/View/clipShape(_:style:)
crawled: 2025-11-30T21:22:28Z
---

# clipShape(_:style:)

**Instance Method**

Sets a clipping shape for this view.

## Declaration

```swift
nonisolated func clipShape<S>(_ shape: S, style: FillStyle = FillStyle()) -> some View where S : Shape

```

## Parameters

- **shape**: The clipping shape to use for this view. The `shape` fills the view’s frame, while maintaining its aspect ratio.
- **style**: The fill style to use when rasterizing `shape`.

## Return Value

A view that clips this view to `shape`, using `style` to define the shape’s rasterization.

## Discussion

Use `clipShape(_:style:)` to clip the view to the provided shape. By applying a clipping shape to a view, you preserve the parts of the view covered by the shape, while eliminating other parts of the view. The clipping shape itself isn’t visible.

For example, this code applies a circular clipping shape to a `Text` view:

```swift
Text("Clipped text in a circle")
    .frame(width: 175, height: 100)
    .foregroundColor(Color.white)
    .background(Color.black)
    .clipShape(Circle())
```

The resulting view shows only the portion of the text that lies within the bounds of the circle.



## Masking and clipping

- **mask(alignment:_:)**: Masks this view using the alpha channel of the given view.
- **clipped(antialiased:)**: Clips this view to its bounding rectangular frame.

