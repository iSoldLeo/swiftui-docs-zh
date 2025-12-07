---
来源： https://developer.apple.com/documentation/SwiftUI/VisualEffect/transform3DEffect(_:)
抓取时间：2025-12-03T06:30:00Z
---

# transform3DEffect(_:)

**实例方法**

对该视图的渲染输出应用 3D 变换。

## 声明

```swift
func transform3DEffect(_ transform: AffineTransform3D) -> some VisualEffect

```

## 参数

- **transform**：应用于视图的三维变换，将视图解释为空间中的三维平面。

## 返回值

根据所提供的`transform`变换渲染的效果

### 应用锚点变换

这不会调整相对于锚点的变换。相反，请使用 [scaleEffect(_:anchor:)](../View/scaleEffect___anchor.zh-Hans.md) 和 [rotation3DEffect(_:anchor:)](../View/rotation3DEffect___anchor.zh-Hans.md) 分别应用缩放和旋转。

```swift
Model3D(url: URL(string: "https://example.com/robot.usdz")!)
   .scaleEffect(transform.scale)
   .rotation3DEffect(transform.rotation ?? .identity)
   .transform3DEffect(AffineTransform3D(
       translation: transform.translation))
```

## 应用变换

- **transformEffect(_:)**：对视图的渲染输出应用仿射变换。


---
source: https://developer.apple.com/documentation/SwiftUI/VisualEffect/transform3DEffect(_:)
crawled: 2025-12-03T06:30:00Z
---

# transform3DEffect(_:)

**Instance Method**

Applies a 3D transformation to this view’s rendered output.

## Declaration

```swift
func transform3DEffect(_ transform: AffineTransform3D) -> some VisualEffect

```

## Parameters

- **transform**: The 3D transformation to apply to the view, interpreting it as a 3D plane in space.

## Return Value

An effect that renders transformed according to the provided `transform`

### Apply a transform about an anchor

This does not adjust the transform relative to an anchor point. Instead, apply the scale and rotation separately using [scaleEffect(_:anchor:)](../View/scaleEffect___anchor.zh-Hans.md) together with [rotation3DEffect(_:anchor:)](../View/rotation3DEffect___anchor.zh-Hans.md).

```swift
Model3D(url: URL(string: "https://example.com/robot.usdz")!)
   .scaleEffect(transform.scale)
   .rotation3DEffect(transform.rotation ?? .identity)
   .transform3DEffect(AffineTransform3D(
       translation: transform.translation))
```

## Applying a transform

- **transformEffect(_:)**: Applies an affine transformation to the view’s rendered output.

