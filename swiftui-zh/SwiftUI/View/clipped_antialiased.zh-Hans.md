--- 来源：https://developer.apple.com/documentation/SwiftUI/View/clipped(antialiased:)

抓取时间：2025-12-02T17:37:23Z

---

# clipped(antialiased:)

**实例方法**

将此视图裁剪到其边界矩形框内。

## 声明

```swift
nonisolated func clipped(antialiased: Bool = false) -> some View

```

## 参数

- **antialiased**：一个布尔值，指示渲染系统是否对裁剪矩形的边缘应用平滑处理。

## 返回值

一个将此视图裁剪到其边界框内的视图。

## 说明

使用 `clipped(antialiased:)` 修饰符可以隐藏超出形状布局边界的任何内容。

默认情况下，视图的边界框仅用于布局，因此超出边界框边缘的内容仍然可见。

```swift
Text("This long text string is clipped")
    .fixedSize()
    .frame(width: 175, height: 100)
    .clipped()
    .border(Color.gray)
```

## 遮罩和裁剪

- **mask(alignment:_:)**：使用给定视图的 Alpha 通道遮罩此视图。

- **clipShape(_:style:)**：为此视图设置裁剪形状。


---
source: https://developer.apple.com/documentation/SwiftUI/View/clipped(antialiased:)
crawled: 2025-12-02T17:37:23Z
---

# clipped(antialiased:)

**Instance Method**

Clips this view to its bounding rectangular frame.

## Declaration

```swift
nonisolated func clipped(antialiased: Bool = false) -> some View

```

## Parameters

- **antialiased**: A Boolean value that indicates whether the rendering system applies smoothing to the edges of the clipping rectangle.

## Return Value

A view that clips this view to its bounding frame.

## Discussion

Use the `clipped(antialiased:)` modifier to hide any content that extends beyond the layout bounds of the shape.

By default, a view’s bounding frame is used only for layout, so any content that extends beyond the edges of the frame is still visible.

```swift
Text("This long text string is clipped")
    .fixedSize()
    .frame(width: 175, height: 100)
    .clipped()
    .border(Color.gray)
```



## Masking and clipping

- **mask(alignment:_:)**: Masks this view using the alpha channel of the given view.
- **clipShape(_:style:)**: Sets a clipping shape for this view.

