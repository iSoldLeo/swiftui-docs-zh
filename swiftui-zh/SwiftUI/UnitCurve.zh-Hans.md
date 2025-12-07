---

来源：https://developer.apple.com/documentation/SwiftUI/UnitCurve
抓取时间：2025-12-02T17:34:02Z

---

# UnitCurve

**Structure**

UnitCurve 函数由一条二维曲线定义，该曲线将 [0,1] 范围内的输入进度映射到同样在 [0,1] 范围内的输出进度。通过改变曲线的形状，可以改变动画或其他插值的有效速度。

## 声明

```swift
struct UnitCurve
```

## 概述

水平 (x) 轴定义输入进度：计算曲线时，必须提供一个 [0,1] 范围内的输入进度值。

垂直 (y) 轴映射到输出进度：计算曲线时，返回与输入进度相交点的 y 分量。

## 获取直线曲线

- **linear**：直线曲线。

## 获取缓动曲线

- **easeIn**：贝塞尔曲线，起始速度较慢，接近终点时速度逐渐加快。

- **easeOut**：贝塞尔曲线，起始速度较快，接近终点时速度逐渐减慢。

- **easeInOut**：贝塞尔曲线，起始速度较慢，中间部分速度逐渐加快，接近终点时速度再次减慢。

- **circularEaseIn**：曲线，起始速度较慢，接近终点时速度逐渐加快。

- **circularEaseOut**：圆弧曲线，起始速度较快，接近终点时速度逐渐减慢。

- **circularEaseInOut**：一条起始速度较慢、中间部分速度加快、末端速度再次减慢的圆形曲线。

## 创建通用贝塞尔曲线

- **bezier(startControlPoint:endControlPoint:)**：使用贝塞尔控制点创建新曲线。

## 反转曲线

- **inverse**：返回曲线的副本，其 x 和 y 分量互换。

## 获取曲线特征

- **value(at:)**：返回给定时间点曲线的输出值（y 分量）。

- **velocity(at:)**：返回给定时间点曲线输出值的变化率（一阶导数）。

## 已弃用符号

- **easeInEaseOut**：贝塞尔曲线，起始速度较慢，中间部分加速，接近末端时再次减速。

## 创建自定义动画

- **CustomAnimation**：定义可动画值随时间变化方式的类型。

- **AnimationContext**：自定义动画可用于管理状态和访问视图环境的上下文值。

- **AnimationState**：存储自定义动画状态的容器。

- **AnimationStateKey**：用于访问动画状态值的键。

- **Spring**：弹簧运动的表示。

## 符合以下规范

- Copyable

- Equatable

- Hashable

- Sendable

- SendableMetatype


---
source: https://developer.apple.com/documentation/SwiftUI/UnitCurve
crawled: 2025-12-02T17:34:02Z
---

# UnitCurve

**Structure**

A  function defined by a two-dimensional curve that maps an input progress in the range [0,1] to an output progress that is also in the range [0,1]. By changing the shape of the curve, the effective speed of an animation or other interpolation can be changed.

## Declaration

```swift
struct UnitCurve
```

## Overview

The horizontal (x) axis defines the input progress: a single input progress value in the range [0,1] must be provided when evaluating a curve.

The vertical (y) axis maps to the output progress: when a curve is evaluated, the y component of the point that intersects the input progress is returned.

## Getting a linear curve

- **linear**: A linear curve.

## Getting easing curves

- **easeIn**: A bezier curve that starts out slowly, then speeds up as it finishes.
- **easeOut**: A bezier curve that starts out quickly, then slows down as it approaches the end.
- **easeInOut**: A bezier curve that starts out slowly, speeds up over the middle, then slows down again as it approaches the end.
- **circularEaseIn**: A curve that starts out slowly, then speeds up as it finishes.
- **circularEaseOut**: A circular curve that starts out quickly, then slows down as it approaches the end.
- **circularEaseInOut**: A circular curve that starts out slowly, speeds up over the middle, then slows down again as it approaches the end.

## Creating a general Bezier curve

- **bezier(startControlPoint:endControlPoint:)**: Creates a new curve using bezier control points.

## Inverting a curve

- **inverse**: Returns a copy of the curve with its x and y components swapped.

## Getting curve characteristics

- **value(at:)**: Returns the output value (y component) of the curve at the given time.
- **velocity(at:)**: Returns the rate of change (first derivative) of the output value of the curve at the given time.

## Deprecated symbols

- **easeInEaseOut**: A bezier curve that starts out slowly, speeds up over the middle, then slows down again as it approaches the end.

## Creating custom animations

- **CustomAnimation**: A type that defines how an animatable value changes over time.
- **AnimationContext**: Contextual values that a custom animation can use to manage state and access a view’s environment.
- **AnimationState**: A container that stores the state for a custom animation.
- **AnimationStateKey**: A key for accessing animation state values.
- **Spring**: A representation of a spring’s motion.

## Conforms To

- Copyable
- Equatable
- Hashable
- Sendable
- SendableMetatype

