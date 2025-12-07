---
来源： https://developer.apple.com/documentation/swiftui/scaledshape
抓取时间： 2025-12-04T11:35:37Z
---

# 缩放形状

**Structure**

应用了缩放变换的形状。

## 声明

```swift
@frozen struct ScaledShape<Content> where Content : Shape
```

## 创建缩放形状

- **init(shape:scale:anchor:)**

## 获取形状的特征

- **anchor**
- **scale**
- **shape**

## 支持类型

- **animatableData**：要制作动画的数据。

## 变换形状

- **RotatedShape**：应用了旋转变换的形状。
- **OffsetShape**：应用了平移偏移变换的形状。
- **TransformedShape**：应用了仿射变换的形状。

## 符合

- 可动画
- 可发送
- 可发送元类型
- 形状
- 查看


---
source: https://developer.apple.com/documentation/swiftui/scaledshape
crawled: 2025-12-04T11:35:37Z
---

# ScaledShape

**Structure**

A shape with a scale transform applied to it.

## Declaration

```swift
@frozen struct ScaledShape<Content> where Content : Shape
```

## Creating a scaled shape

- **init(shape:scale:anchor:)**

## Getting the shape’s characteristics

- **anchor**
- **scale**
- **shape**

## Supporting types

- **animatableData**: The data to animate.

## Transforming a shape

- **RotatedShape**: A shape with a rotation transform applied to it.
- **OffsetShape**: A shape with a translation offset transform applied to it.
- **TransformedShape**: A shape with an affine transform applied to it.

## Conforms To

- Animatable
- Sendable
- SendableMetatype
- Shape
- View

