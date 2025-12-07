--- 来源：https://developer.apple.com/documentation/swiftui/animatable
抓取时间：2025-12-03T06:15:12Z

---

# 可动画属性

**Protocol**

描述如何为视图的属性添加动画效果的类型。

## 声明

```swift
protocol Animatable
```

## 数据动画

- **Animatable()**：成员和扩展宏，当应用于结构体、类或枚举声明时，它会综合满足 `Animatable` 及其要求，即使用应用此宏的类型的现有可动画属性来为 `animatableData` 属性添加动画效果。

- **AnimatableIgnored()**：一个访问器宏，用于标记要从 `animatableData` 合成中排除的类型属性：

- **animatableData**：要动画化的数据。

- **AnimatableData**：定义要动画化的数据的类型。

## 使数据可动画化

- **AnimatableValues**

- **AnimatablePair**：一对可动画化的值，它们本身也是可动画化的。

- **VectorArithmetic**：可以作为可动画化类型的可动画化数据的类型。

- **EmptyAnimatableData**：用于可动画化数据的空类型。

## 继承自

- AnimatableModifier

- GeometryEffect

- InsettableShape

- Layout

- RoundedRectangularShape

- Shape

- TextRenderer

- VisualEffect

## 兼容类型

- Angle

- AnyLayout

- AnyShape

- ButtonBorderShape

- Capsule

- Circle

- Color.Resolved

- Color.ResolvedHDR

- ConcentricRectangle

- ContainerRelativeShape

- DefaultGlassEffectShape

- Edge.Corner.Style

- EdgeInsets

- EdgeInsets3D

- Ellipse

- EmptyVisualEffect

- GridLayout

- HStackLayout

- LayoutRotationUnaryLayout

- ModifiedContent

- OffsetShape

- Path

- Rectangle
- RectangleCornerRadii
- RotatedShape
- RoundedRectangle
-圆角矩形形状的角

- 缩放形状

- 空间容器

- 描边样式

- 变换形状

- 不规则圆角矩形

- 单位点

- 3D 单位点

- V 型堆栈布局

- Z 型堆栈布局


---
source: https://developer.apple.com/documentation/swiftui/animatable
crawled: 2025-12-03T06:15:12Z
---

# Animatable

**Protocol**

A type that describes how to animate a property of a view.

## Declaration

```swift
protocol Animatable
```

## Animating data

- **Animatable()**: A member and extension macro that, when applied to a struct, class or enum declaration, synthesizes the conformance to `Animatable` and its requirement, the `animatableData` property using the existing animatable properties of the type this macro is applied to.
- **AnimatableIgnored()**: An accessor macro that marks a property of a type to be excluded from the `animatableData` synthesis:
- **animatableData**: The data to animate.
- **AnimatableData**: The type defining the data to animate.

## Making data animatable

- **AnimatableValues**
- **AnimatablePair**: A pair of animatable values, which is itself animatable.
- **VectorArithmetic**: A type that can serve as the animatable data of an animatable type.
- **EmptyAnimatableData**: An empty type for animatable data.

## Inherited By

- AnimatableModifier
- GeometryEffect
- InsettableShape
- Layout
- RoundedRectangularShape
- Shape
- TextRenderer
- VisualEffect

## Conforming Types

- Angle
- AnyLayout
- AnyShape
- ButtonBorderShape
- Capsule
- Circle
- Color.Resolved
- Color.ResolvedHDR
- ConcentricRectangle
- ContainerRelativeShape
- DefaultGlassEffectShape
- Edge.Corner.Style
- EdgeInsets
- EdgeInsets3D
- Ellipse
- EmptyVisualEffect
- GridLayout
- HStackLayout
- LayoutRotationUnaryLayout
- ModifiedContent
- OffsetShape
- Path
- Rectangle
- RectangleCornerRadii
- RotatedShape
- RoundedRectangle
- RoundedRectangularShapeCorners
- ScaledShape
- SpatialContainer
- StrokeStyle
- TransformedShape
- UnevenRoundedRectangle
- UnitPoint
- UnitPoint3D
- VStackLayout
- ZStackLayout

