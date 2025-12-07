---
来源： https://developer.apple.com/documentation/swiftui/vectorarithmetic
抓取时间： 2025-12-03T06:15:09Z
---

# 矢量算术

**Protocol**

可作为动画类型的动画数据的类型。

## 声明

```swift
protocol VectorArithmetic : AdditiveArithmetic
```

## 概览

`VectorArithmetic`扩展了`AdditiveArithmetic`协议的标量乘法功能，并提供了查询值的矢量幅度的方法。使用该类型作为符合[Animatable](Animatable.zh-Hans.md) 协议的类型的`animatableData` 关联类型。

## 操作值

- **magnitudeSquared**：返回此向量算术实例与自身的点积。
- **scale(by:)**：将此值的每个分量与给定值相乘。
- **scaled(by:)**：返回该值的每个分量乘以给定值的值。
- **interpolate(towards:amount:)**：将此值与`other` 插值，并乘以指定的`amount`。
- **interpolated(towards:amount:)**：用`other` 内插指定的`amount`，返回该值。

## 制作动画数据

- **Animatable**：描述如何使视图属性动画化的类型。
- **AnimatableValues**：描述如何使视图属性动画化的类型。
- **AnimatablePair**：一对可动画化的值，其本身也是可动画化的。
- **EmptyAnimatableData**：动画数据的空类型。

## 继承自

- 加法算术
- 等价

## 符合类型

- 动画对
- 动画值
- 空动画数据


---
source: https://developer.apple.com/documentation/swiftui/vectorarithmetic
crawled: 2025-12-03T06:15:09Z
---

# VectorArithmetic

**Protocol**

A type that can serve as the animatable data of an animatable type.

## Declaration

```swift
protocol VectorArithmetic : AdditiveArithmetic
```

## Overview

`VectorArithmetic` extends the `AdditiveArithmetic` protocol with scalar multiplication and a way to query the vector magnitude of the value. Use this type as the `animatableData` associated type of a type that conforms to the [Animatable](Animatable.zh-Hans.md) protocol.

## Manipulating values

- **magnitudeSquared**: Returns the dot-product of this vector arithmetic instance with itself.
- **scale(by:)**: Multiplies each component of this value by the given value.
- **scaled(by:)**: Returns a value with each component of this value multiplied by the given value.
- **interpolate(towards:amount:)**: Interpolates this value with `other` by the specified `amount`.
- **interpolated(towards:amount:)**: Returns this value interpolated with `other` by the specified `amount`.

## Making data animatable

- **Animatable**: A type that describes how to animate a property of a view.
- **AnimatableValues**
- **AnimatablePair**: A pair of animatable values, which is itself animatable.
- **EmptyAnimatableData**: An empty type for animatable data.

## Inherits From

- AdditiveArithmetic
- Equatable

## Conforming Types

- AnimatablePair
- AnimatableValues
- EmptyAnimatableData

