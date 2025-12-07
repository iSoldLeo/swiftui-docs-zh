---
来源：https://developer.apple.com/documentation/SwiftUI/GraphicsContext/Shading/linearGradient(_:startPoint:endPoint:options:)
抓取时间： 2025-12-01T22:05:03Z
---

# linearGradient(_:startPoint:endPoint:options:)

**类型方法**

返回一个填充线性（轴向）梯度的阴影实例。

## 声明

```swift
static func linearGradient(_ gradient: Gradient, startPoint: CGPoint, endPoint: CGPoint, options: GraphicsContext.GradientOptions = GradientOptions()) -> GraphicsContext.Shading
```

## 参数

- **gradient**：定义渐变颜色的 [Gradient](../../Gradient.zh-Hans.md) 实例。
- **startPoint**：梯度轴的起点。
- **endPoint**：渐变轴的起点：梯度轴的终点。
- **options**：用于配置渐变的选项。

## 返回值

一个填充了线性梯度的阴影实例。

## 讨论

着色实例在当前用户空间中定义了一条从`startPoint`到`endPoint`的轴线，并将`gradient`的颜色映射到垂直于轴线的线条上。

## 梯度

- **radialGradient(_:center:startRadius:endRadius:options:)**：返回一个填充径向渐变的阴影实例。
- **conicGradient(_:center:angle:options:)**：返回填充圆锥形（角度）渐变的阴影实例。


---
source: https://developer.apple.com/documentation/SwiftUI/GraphicsContext/Shading/linearGradient(_:startPoint:endPoint:options:)
crawled: 2025-12-01T22:05:03Z
---

# linearGradient(_:startPoint:endPoint:options:)

**Type Method**

Returns a shading instance that fills a linear (axial) gradient.

## Declaration

```swift
static func linearGradient(_ gradient: Gradient, startPoint: CGPoint, endPoint: CGPoint, options: GraphicsContext.GradientOptions = GradientOptions()) -> GraphicsContext.Shading
```

## Parameters

- **gradient**: A [Gradient](../../Gradient.zh-Hans.md) instance that defines the colors of the gradient.
- **startPoint**: The start point of the gradient axis.
- **endPoint**: The end point of the gradient axis.
- **options**: Options that you use to configure the gradient.

## Return Value

A shading instance filled with a linear gradient.

## Discussion

The shading instance defines an axis from `startPoint` to `endPoint` in the current user space and maps colors from `gradient` to lines perpendicular to the axis.

## Gradients

- **radialGradient(_:center:startRadius:endRadius:options:)**: Returns a shading instance that fills a radial gradient.
- **conicGradient(_:center:angle:options:)**: Returns a shading instance that fills a conic (angular) gradient.

