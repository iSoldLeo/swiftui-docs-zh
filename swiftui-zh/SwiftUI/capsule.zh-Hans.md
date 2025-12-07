---
来源： https://developer.apple.com/documentation/swiftui/capsule
抓取时间： 2025-12-04T11:33:49Z
---

# 胶囊

**Structure**

在视图框架内对齐的胶囊形状。

## 声明

```swift
@frozen struct Capsule
```

## 概览

胶囊形状相当于一个圆角矩形，其角半径选为矩形最小边长的一半。

## 创建胶囊

- **init(style:)**：创建一个新的胶囊形状。

## 获取形状特征

- **style**: 创建新的胶囊形状。

## 创建圆形形状

- **Circle**：以包含它的视图的边框为中心的圆。
- **Ellipse**：在包含它的视图框架内对齐的椭圆。

## 符合

- 可动画
- 可复制
- 可嵌入形状
- 圆角矩形
- 可发送
- 可发送元类型
- 形状
- 查看


---
source: https://developer.apple.com/documentation/swiftui/capsule
crawled: 2025-12-04T11:33:49Z
---

# Capsule

**Structure**

A capsule shape aligned inside the frame of the view containing it.

## Declaration

```swift
@frozen struct Capsule
```

## Overview

A capsule shape is equivalent to a rounded rectangle where the corner radius is chosen as half the length of the rectangle’s smallest edge.

## Creating a capsule

- **init(style:)**: Creates a new capsule shape.

## Getting the shape’s characteristics

- **style**

## Creating circular shapes

- **Circle**: A circle centered on the frame of the view containing it.
- **Ellipse**: An ellipse aligned inside the frame of the view containing it.

## Conforms To

- Animatable
- Copyable
- InsettableShape
- RoundedRectangularShape
- Sendable
- SendableMetatype
- Shape
- View

