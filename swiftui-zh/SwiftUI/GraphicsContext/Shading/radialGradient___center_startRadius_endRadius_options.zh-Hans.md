---
来源：https://developer.apple.com/documentation/SwiftUI/GraphicsContext/Shading/radialGradient(_:center:startRadius:endRadius:options:)
抓取时间：2025-12-03T17:19:46Z
---

# radialGradient(_:center:startRadius:endRadius:options:)

**类型方法**

返回一个填充径向梯度的阴影实例。

## 声明

```swift
static func radialGradient(_ gradient: Gradient, center: CGPoint, startRadius: CGFloat, endRadius: CGFloat, options: GraphicsContext.GradientOptions = GradientOptions()) -> GraphicsContext.Shading
```

## 参数

- **gradient**：定义渐变颜色的 [Gradient](../../Gradient.zh-Hans.md) 实例。
- **center**：SwiftUI 将梯度居中的当前用户空间中的点。
- **startRadius**：从中心点到梯度起点的距离。
- **endRadius**：从中心到梯度终点的距离。
- **options**：用于配置渐变的选项。

## 返回值

一个填充了径向渐变的阴影实例。

## 梯度

- **linearGradient(_:startPoint:endPoint:options:)**：返回一个填充线性（轴向）渐变的阴影实例。
- **conicGradient(_:center:angle:options:)**：返回填充圆锥形（角度）渐变的阴影实例。


---
source: https://developer.apple.com/documentation/SwiftUI/GraphicsContext/Shading/radialGradient(_:center:startRadius:endRadius:options:)
crawled: 2025-12-03T17:19:46Z
---

# radialGradient(_:center:startRadius:endRadius:options:)

**Type Method**

Returns a shading instance that fills a radial gradient.

## Declaration

```swift
static func radialGradient(_ gradient: Gradient, center: CGPoint, startRadius: CGFloat, endRadius: CGFloat, options: GraphicsContext.GradientOptions = GradientOptions()) -> GraphicsContext.Shading
```

## Parameters

- **gradient**: A [Gradient](../../Gradient.zh-Hans.md) instance that defines the colors of the gradient.
- **center**: The point in the current user space on which SwiftUI centers the gradient.
- **startRadius**: The distance from the center where the gradient starts.
- **endRadius**: The distance from the center where the gradient ends.
- **options**: Options that you use to configure the gradient.

## Return Value

A shading instance filled with a radial gradient.

## Gradients

- **linearGradient(_:startPoint:endPoint:options:)**: Returns a shading instance that fills a linear (axial) gradient.
- **conicGradient(_:center:angle:options:)**: Returns a shading instance that fills a conic (angular) gradient.

