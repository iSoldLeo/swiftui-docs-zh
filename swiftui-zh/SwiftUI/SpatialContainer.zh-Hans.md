--- 来源：https://developer.apple.com/documentation/SwiftUI/SpatialContainer
抓取时间：2025-12-02T17:38:53Z

---

# SpatialContainer

**Structure**

一个用于在 3D 空间中对齐重叠内容的布局容器。

## 声明

```swift
@frozen struct SpatialContainer
```

## 概述

该容器将采用其每个子元素各维度的最大值，并根据 `alignment` 对齐子元素。

## 初始化器

- **init(alignment:)**：创建具有指定 3D 对齐方式的空间容器布局。

## 对齐视图

- **在堆栈中对齐视图**：使用对齐参考线在堆栈中定位视图。

- **跨堆栈对齐视图**：创建自定义对齐方式，并使用它来对齐多个堆栈中的视图。

- **alignmentGuide(_:computeValue:)**：设置视图的水平对齐方式。

- **Alignment**：在两个轴上对齐。

- **HorizontalAlignment**：沿水平轴的对齐位置。

- **VerticalAlignment**：沿垂直轴的对齐位置。

- **DepthAlignment**：沿深度轴的对齐位置。

- **AlignmentID**：用于创建自定义对齐参考线的类型。

- **ViewDimensions**：视图在其自身坐标空间中的大小和对齐参考线。

- **ViewDimensions3D**：视图在其自身坐标空间中的三维尺寸和对齐方式指南。

## 符合以下条件

- 可动画化

- 可复制

- 布局

- 可发送

- 可发送元类型


---
source: https://developer.apple.com/documentation/SwiftUI/SpatialContainer
crawled: 2025-12-02T17:38:53Z
---

# SpatialContainer

**Structure**

A layout container that aligns overlapping content in 3D space.

## Declaration

```swift
@frozen struct SpatialContainer
```

## Overview

The container will take the max size of each dimension of each of its children, aligning its children based on the `alignment`.

## Initializers

- **init(alignment:)**: Creates a spatial container layout with the specified 3D alignment.

## Aligning views

- **Aligning views within a stack**: Position views inside a stack using alignment guides.
- **Aligning views across stacks**: Create a custom alignment and use it to align views across multiple stacks.
- **alignmentGuide(_:computeValue:)**: Sets the view’s horizontal alignment.
- **Alignment**: An alignment in both axes.
- **HorizontalAlignment**: An alignment position along the horizontal axis.
- **VerticalAlignment**: An alignment position along the vertical axis.
- **DepthAlignment**: An alignment position along the depth axis.
- **AlignmentID**: A type that you use to create custom alignment guides.
- **ViewDimensions**: A view’s size and alignment guides in its own coordinate space.
- **ViewDimensions3D**: A view’s 3D size and alignment guides in its own coordinate space.

## Conforms To

- Animatable
- Copyable
- Layout
- Sendable
- SendableMetatype

