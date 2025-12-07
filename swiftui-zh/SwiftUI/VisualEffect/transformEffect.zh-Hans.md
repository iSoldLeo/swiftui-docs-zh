---
来源： https://developer.apple.com/documentation/SwiftUI/VisualEffect/transformEffect(_:)
抓取时间： 2025-12-01T11:19:09Z
---

# transformEffect(_:)

**实例方法**

对视图的渲染输出应用仿射变换。

## 声明

```swift
func transformEffect(_ transform: CGAffineTransform) -> some VisualEffect

```

## 参数

- **transform**：要应用于视图的[doc://com.apple.documentation/documentation/CoreFoundation/CGAffineTransform]。

## 返回值

对视图的渲染输出应用仿射变换的效果。

## 讨论

使用 `transformEffect(_:)` 可以根据提供的 [doc://com.apple.documentation/documentation/CoreFoundation/CGAffineTransform] 旋转、缩放、平移或倾斜视图的输出。

## 应用变换

- **transform3DEffect(_:)**：对该视图的渲染输出应用 3D 变换。


---
source: https://developer.apple.com/documentation/SwiftUI/VisualEffect/transformEffect(_:)
crawled: 2025-12-01T11:19:09Z
---

# transformEffect(_:)

**Instance Method**

Applies an affine transformation to the view’s rendered output.

## Declaration

```swift
func transformEffect(_ transform: CGAffineTransform) -> some VisualEffect

```

## Parameters

- **transform**: A [doc://com.apple.documentation/documentation/CoreFoundation/CGAffineTransform] to apply to the view.

## Return Value

An effect that applies an affine transformation to the view’s rendered output.

## Discussion

Use `transformEffect(_:)` to rotate, scale, translate, or skew the output of the view according to the provided [doc://com.apple.documentation/documentation/CoreFoundation/CGAffineTransform].

## Applying a transform

- **transform3DEffect(_:)**: Applies a 3D transformation to this view’s rendered output.

