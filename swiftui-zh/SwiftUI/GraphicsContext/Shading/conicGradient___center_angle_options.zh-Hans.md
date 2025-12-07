---
来源：https://developer.apple.com/documentation/SwiftUI/GraphicsContext/Shading/conicGradient(_:中心:角度:选项:)
抓取时间：2025-12-01T22:05:05Z
---

# conicGradient(_:center:angle:options:)

**类型方法**

返回一个填充圆锥（角度）梯度的阴影实例。

## 声明

```swift
static func conicGradient(_ gradient: Gradient, center: CGPoint, angle: Angle = Angle(), options: GraphicsContext.GradientOptions = GradientOptions()) -> GraphicsContext.Shading
```

## 参数

- **gradient**：定义渐变颜色的 [Gradient](../../Gradient.zh-Hans.md) 实例。
- **center**：SwiftUI 将梯度居中的当前用户空间中的点。
- **angle**：SwiftUI 开始和结束渐变时使用的与中心点的夹角。梯度会一直围绕中心扫过。
- **options**：用于配置渐变的选项。

## 返回值

一个填充了圆锥梯度的阴影实例。

## 梯度

- **linearGradient(_:startPoint:endPoint:options:)**：返回一个填充线性（轴向）梯度的阴影实例。
- **radialGradient(_:center:startRadius:endRadius:options:)**：返回一个填充径向渐变的阴影实例。


---
source: https://developer.apple.com/documentation/SwiftUI/GraphicsContext/Shading/conicGradient(_:center:angle:options:)
crawled: 2025-12-01T22:05:05Z
---

# conicGradient(_:center:angle:options:)

**Type Method**

Returns a shading instance that fills a conic (angular) gradient.

## Declaration

```swift
static func conicGradient(_ gradient: Gradient, center: CGPoint, angle: Angle = Angle(), options: GraphicsContext.GradientOptions = GradientOptions()) -> GraphicsContext.Shading
```

## Parameters

- **gradient**: A [Gradient](../../Gradient.zh-Hans.md) instance that defines the colors of the gradient.
- **center**: The point in the current user space on which SwiftUI centers the gradient.
- **angle**: The angle about the center that SwiftUI uses to start and finish the gradient. The gradient sweeps all the way around the center.
- **options**: Options that you use to configure the gradient.

## Return Value

A shading instance filled with a conic gradient.

## Gradients

- **linearGradient(_:startPoint:endPoint:options:)**: Returns a shading instance that fills a linear (axial) gradient.
- **radialGradient(_:center:startRadius:endRadius:options:)**: Returns a shading instance that fills a radial gradient.

