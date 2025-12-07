---
来源： https://developer.apple.com/documentation/swiftui/transformedshape
抓取时间： 2025-12-04T11:35:58Z
---

# 变形形状

**Structure**

应用了仿射变换的形状。

## 声明

```swift
@frozen struct TransformedShape<Content> where Content : Shape
```

## 创建变换后的形状

- **init(shape:transform:)**

## 获取形状的特征

- **shape**
- **transform**

## 变换形状

- **ScaledShape**：应用了缩放变换的形状。
- **RotatedShape**：应用了旋转变换的形状。
- **OffsetShape**：应用了平移偏移变换的形状。

## 符合

- 可动画
- 可发送
- 可发送元类型
- 形状
- 查看


---
source: https://developer.apple.com/documentation/swiftui/transformedshape
crawled: 2025-12-04T11:35:58Z
---

# TransformedShape

**Structure**

A shape with an affine transform applied to it.

## Declaration

```swift
@frozen struct TransformedShape<Content> where Content : Shape
```

## Creating a transformed shape

- **init(shape:transform:)**

## Getting the shape’s characteristics

- **shape**
- **transform**

## Transforming a shape

- **ScaledShape**: A shape with a scale transform applied to it.
- **RotatedShape**: A shape with a rotation transform applied to it.
- **OffsetShape**: A shape with a translation offset transform applied to it.

## Conforms To

- Animatable
- Sendable
- SendableMetatype
- Shape
- View

