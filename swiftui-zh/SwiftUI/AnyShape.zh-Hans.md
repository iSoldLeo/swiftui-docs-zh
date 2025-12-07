--- 来源：https://developer.apple.com/documentation/SwiftUI/AnyShape
抓取时间：2025-12-02T17:26:38Z

---

# AnyShape

**Structure**

一个已擦除类型的形状值。

## 声明

```swift
@frozen struct AnyShape
```

## 概述

您可以使用此类型动态切换形状类型：

```swift
struct MyClippedView: View {
    var isCircular: Bool

    var body: some View {
        OtherView().clipShape(isCircular ?
            AnyShape(Circle()) : AnyShape(Capsule()))
    }
}
```

## 创建形状

- **init(_:)**：从形状创建 AnyShape 实例。

## 定义形状行为

- **ShapeView**：提供一个可用于绘制操作的形状的视图。

- **Shape**：一个可在绘制视图时使用的 2D 形状。

- **ShapeRole**：形状样式设置方式。

- **StrokeStyle**：描边路径的特征。

- **StrokeShapeView**：描边形状提供程序。

- **StrokeBorderShapeView**：描边形状提供程序。

- **FillStyle**：栅格化矢量形状的样式。

- **FillShapeView**：填充形状提供程序。

## 符合以下标准

- Animatable

- Sendable

- SendableMetatype

- Shape

- View


---
source: https://developer.apple.com/documentation/SwiftUI/AnyShape
crawled: 2025-12-02T17:26:38Z
---

# AnyShape

**Structure**

A type-erased shape value.

## Declaration

```swift
@frozen struct AnyShape
```

## Overview

You can use this type to dynamically switch between shape types:

```swift
struct MyClippedView: View {
    var isCircular: Bool

    var body: some View {
        OtherView().clipShape(isCircular ?
            AnyShape(Circle()) : AnyShape(Capsule()))
    }
}
```

## Creating a shape

- **init(_:)**: Create an any shape instance from a shape.

## Defining shape behavior

- **ShapeView**: A view that provides a shape that you can use for drawing operations.
- **Shape**: A 2D shape that you can use when drawing a view.
- **ShapeRole**: Ways of styling a shape.
- **StrokeStyle**: The characteristics of a stroke that traces a path.
- **StrokeShapeView**: A shape provider that strokes its shape.
- **StrokeBorderShapeView**: A shape provider that strokes the border of its shape.
- **FillStyle**: A style for rasterizing vector shapes.
- **FillShapeView**: A shape provider that fills its shape.

## Conforms To

- Animatable
- Sendable
- SendableMetatype
- Shape
- View

