---
来源： https://developer.apple.com/documentation/SwiftUI/ViewDimensions3D
抓取时间： 2025-12-02T17:38:52Z
---

# ViewDimensions3D

**Structure**

视图在自身坐标空间中的三维尺寸和对齐指引。

## 声明

```swift
struct ViewDimensions3D
```

## 实例属性

- **depth**：视图的深度。
- **height**：视图的深度：景物的高度。
- **width**：视图的宽度。

## 下标

- **subscript(_:)**：获取给定深度指南的值。
- **subscript(explicit:)**：获取给定深度排列向导的显式值

## 对齐视图

- 在堆栈内对齐视图**：使用排列向导在堆栈内定位视图。
- 跨堆栈对齐视图**：创建自定义对齐方式，并使用它在多个堆栈中对齐视图。
- **alignmentGuide(_:computeValue:)**：设置视图的水平对齐方式。
- **Alignment**：设置视图的水平对齐方式：双轴对齐。
- **HorizontalAlignment**：沿水平轴的对齐位置。
- **VerticalAlignment**： 沿垂直轴对齐的位置：沿垂直轴对齐的位置。
- **DepthAlignment**： 沿纵轴的对齐位置：沿深度轴的对齐位置。
- **AlignmentID**：用于创建自定义对齐导轨的类型。
- **ViewDimensions**：视图在其自身坐标空间中的尺寸和对齐方式向导。
- **SpatialContainer**：在三维空间中对齐重叠内容的布局容器。

## 符合

- 可复制
- 等价


---
source: https://developer.apple.com/documentation/SwiftUI/ViewDimensions3D
crawled: 2025-12-02T17:38:52Z
---

# ViewDimensions3D

**Structure**

A view’s 3D size and alignment guides in its own coordinate space.

## Declaration

```swift
struct ViewDimensions3D
```

## Instance Properties

- **depth**: The view’s depth.
- **height**: The view’s height.
- **width**: The view’s width.

## Subscripts

- **subscript(_:)**: Gets the value of the given depth guide.
- **subscript(explicit:)**: Gets the explicit value of the given depth alignment guide

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
- **SpatialContainer**: A layout container that aligns overlapping content in 3D space.

## Conforms To

- Copyable
- Equatable

