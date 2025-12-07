--- 来源：https://developer.apple.com/documentation/swiftui/animatablepair
抓取时间：2025-12-03T06:15:13Z

---

# AnimatablePair

**Structure**

一对可动画的值，它们本身也是可动画的。

## 声明

```swift
@frozen struct AnimatablePair<First, Second> where First : VectorArithmetic, Second : VectorArithmetic
```

## 创建可动画对

- **init(_:_:)**：使用提供的值创建一个动画对。

## 获取组成动画

- **first**：第一个值。

- **second**：第二个值。

## 操作值

- **magnitudeSquared**：此动画对与其自身的点积。

## 使数据可动画化

- **Animatable**：描述如何为视图的属性添加动画的类型。

- **AnimatableValues**

- **VectorArithmetic**：可作为可动画类型的可动画数据的类型。

- **EmptyAnimatableData**：用于可动画数据的空类型。

## 符合以下规范

- AdditiveArithmetic

- Equatable

- Sendable

- SendableMetatype

- VectorArithmetic


---
source: https://developer.apple.com/documentation/swiftui/animatablepair
crawled: 2025-12-03T06:15:13Z
---

# AnimatablePair

**Structure**

A pair of animatable values, which is itself animatable.

## Declaration

```swift
@frozen struct AnimatablePair<First, Second> where First : VectorArithmetic, Second : VectorArithmetic
```

## Creating an animatable pair

- **init(_:_:)**: Creates an animated pair with the provided values.

## Getting the constituent animations

- **first**: The first value.
- **second**: The second value.

## Manipulating values

- **magnitudeSquared**: The dot-product of this animated pair with itself.

## Making data animatable

- **Animatable**: A type that describes how to animate a property of a view.
- **AnimatableValues**
- **VectorArithmetic**: A type that can serve as the animatable data of an animatable type.
- **EmptyAnimatableData**: An empty type for animatable data.

## Conforms To

- AdditiveArithmetic
- Equatable
- Sendable
- SendableMetatype
- VectorArithmetic

