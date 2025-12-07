---
来源： https://developer.apple.com/documentation/swiftui/emptyanimatabledata
抓取时间： 2025-12-03T06:15:14Z
---

# EmptyAnimatableData

**Structure**

动画数据的空类型。

## 声明

```swift
@frozen struct EmptyAnimatableData
```

## 概览

该类型适合用作没有任何动画属性的类型的 `animatableData` 属性。

## 创建数据

- **init()**属性

## 操作数据

- **magnitudeSquared**：该动画数据实例与自身的点积。

## 使数据动画化

- **Animatable**：描述如何使视图属性动画化的类型。
- **AnimatableValues**：描述如何将视图属性动画化的类型。
- **AnimatablePair**：一对可动画化的值，其本身也是可动画化的。
- **VectorArithmetic**：可作为动画类型的动画数据的类型。

## 符合

- 加法算术
- 比特可复制
- 可复制
- 可等价
- 可发送
- 可发送元类型
- 矢量算术


---
source: https://developer.apple.com/documentation/swiftui/emptyanimatabledata
crawled: 2025-12-03T06:15:14Z
---

# EmptyAnimatableData

**Structure**

An empty type for animatable data.

## Declaration

```swift
@frozen struct EmptyAnimatableData
```

## Overview

This type is suitable for use as the `animatableData` property of types that do not have any animatable properties.

## Creating the data

- **init()**

## Manipulating the data

- **magnitudeSquared**: The dot-product of this animatable data instance with itself.

## Making data animatable

- **Animatable**: A type that describes how to animate a property of a view.
- **AnimatableValues**
- **AnimatablePair**: A pair of animatable values, which is itself animatable.
- **VectorArithmetic**: A type that can serve as the animatable data of an animatable type.

## Conforms To

- AdditiveArithmetic
- BitwiseCopyable
- Copyable
- Equatable
- Sendable
- SendableMetatype
- VectorArithmetic

