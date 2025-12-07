---
来源： https://developer.apple.com/documentation/swiftui/rotatedshape
抓取时间：2025-12-04T11:35:17Z
---

# 旋转形状

**Structure**

应用了旋转变换的形状。

## 声明

```swift
@frozen struct RotatedShape<Content> where Content : Shape
```

## 创建旋转形状

- **init(shape:angle:anchor:)**

## 获取形状的特征

- **anchor**
- **angle**
- **shape**

## 支持类型

- **animatableData**：要制作动画的数据。

## 变换形状

- **ScaledShape**：应用了缩放变换的形状。
- **OffsetShape**：应用了平移偏移变换的形状。
- **TransformedShape**：应用了仿射变换的形状。

## 符合

- 可动画
- 可复制
- 可嵌入形状
- 可发送
- 可发送元类型
- 形状
- 查看


---
source: https://developer.apple.com/documentation/swiftui/rotatedshape
crawled: 2025-12-04T11:35:17Z
---

# RotatedShape

**Structure**

A shape with a rotation transform applied to it.

## Declaration

```swift
@frozen struct RotatedShape<Content> where Content : Shape
```

## Creating a rotated shape

- **init(shape:angle:anchor:)**

## Getting the shape’s characteristics

- **anchor**
- **angle**
- **shape**

## Supporting types

- **animatableData**: The data to animate.

## Transforming a shape

- **ScaledShape**: A shape with a scale transform applied to it.
- **OffsetShape**: A shape with a translation offset transform applied to it.
- **TransformedShape**: A shape with an affine transform applied to it.

## Conforms To

- Animatable
- Copyable
- InsettableShape
- Sendable
- SendableMetatype
- Shape
- View

