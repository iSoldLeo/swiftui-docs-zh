--- 来源：https://developer.apple.com/documentation/SwiftUI/View/mask(alignment:_:)

抓取时间：2025-12-02T17:37:22Z

---

# mask(alignment:_:)

**实例方法**

使用给定视图的 alpha 通道遮罩当前视图。

## 声明

```swift
nonisolated func mask<Mask>(alignment: Alignment = .center, @ViewBuilder _ mask: () -> Mask) -> some View where Mask : View

```

## 参数

- **alignment**：`mask` 相对于当前视图的对齐方式。

- **mask**：渲染系统将 alpha 值应用于指定视图的视图。

## 说明

当您想要将另一个视图的 alpha（不透明度）值应用于当前视图时，请使用 `mask(_:)`。

此示例展示了一个被不透明度为 10% 的矩形遮罩的图像：

```swift
Image(systemName: "envelope.badge.fill")
    .foregroundColor(Color.blue)
    .font(.system(size: 128, weight: .regular))
    .mask {
        Rectangle().opacity(0.1)
    }
```

## 遮罩和裁剪

- **clipped(antialiased:)**：将此视图裁剪到其边界矩形框内。

- **clipShape(_:style:)**：为此视图设置裁剪形状。


---
source: https://developer.apple.com/documentation/SwiftUI/View/mask(alignment:_:)
crawled: 2025-12-02T17:37:22Z
---

# mask(alignment:_:)

**Instance Method**

Masks this view using the alpha channel of the given view.

## Declaration

```swift
nonisolated func mask<Mask>(alignment: Alignment = .center, @ViewBuilder _ mask: () -> Mask) -> some View where Mask : View

```

## Parameters

- **alignment**: The alignment for `mask` in relation to this view.
- **mask**: The view whose alpha the rendering system applies to the specified view.

## Discussion

Use `mask(_:)` when you want to apply the alpha (opacity) value of another view to the current view.

This example shows an image masked by rectangle with a 10% opacity:

```swift
Image(systemName: "envelope.badge.fill")
    .foregroundColor(Color.blue)
    .font(.system(size: 128, weight: .regular))
    .mask {
        Rectangle().opacity(0.1)
    }
```



## Masking and clipping

- **clipped(antialiased:)**: Clips this view to its bounding rectangular frame.
- **clipShape(_:style:)**: Sets a clipping shape for this view.

