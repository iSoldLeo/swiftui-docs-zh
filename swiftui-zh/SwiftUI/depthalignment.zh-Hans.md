---
来源： https://developer.apple.com/documentation/swiftui/depthalignment
抓取时间： 2025-12-04T13:32:27Z
---

# 深度对齐

**Structure**

沿深度轴的对齐位置。

## 声明

```swift
@frozen struct DepthAlignment
```

## 获取指南

- **back**：标记视图底边的向导。
- **center**：标记视图垂直中心的导线。
- **front**：标记视图顶部边缘的导线。

## 初始化器

- **init(_:)**

## 实例方法

- **combineExplicit(_:)**

## 对齐视图

- 在堆叠内对齐视图**：使用对齐向导在堆栈内定位视图。
- 跨堆栈对齐视图**：创建自定义对齐方式，并使用它在多个堆栈中对齐视图。
- **alignmentGuide(_:computeValue:)**：设置视图的水平对齐方式。
- **Alignment**：设置视图的水平对齐方式：双轴对齐。
- **HorizontalAlignment**：沿水平轴的对齐位置。
- **VerticalAlignment**： 沿垂直轴对齐的位置：沿垂直轴对齐的位置。
- **AlignmentID**：用于创建自定义对齐导轨的类型。
- **ViewDimensions**：视图在其自身坐标空间中的尺寸和对齐方式向导。
- **ViewDimensions3D**：视图在其自身坐标空间中的三维尺寸和排列向导。
- **SpatialContainer**：在三维空间中对齐重叠内容的布局容器。

## 符合

- 等价
- 可发送
- 可发送元数据类型


---
source: https://developer.apple.com/documentation/swiftui/depthalignment
crawled: 2025-12-04T13:32:27Z
---

# DepthAlignment

**Structure**

An alignment position along the depth axis.

## Declaration

```swift
@frozen struct DepthAlignment
```

## Getting guides

- **back**: A guide marking the bottom edge of the view.
- **center**: A guide marking the vertical center of the view.
- **front**: A guide marking the top edge of the view.

## Initializers

- **init(_:)**

## Instance Methods

- **combineExplicit(_:)**

## Aligning views

- **Aligning views within a stack**: Position views inside a stack using alignment guides.
- **Aligning views across stacks**: Create a custom alignment and use it to align views across multiple stacks.
- **alignmentGuide(_:computeValue:)**: Sets the view’s horizontal alignment.
- **Alignment**: An alignment in both axes.
- **HorizontalAlignment**: An alignment position along the horizontal axis.
- **VerticalAlignment**: An alignment position along the vertical axis.
- **AlignmentID**: A type that you use to create custom alignment guides.
- **ViewDimensions**: A view’s size and alignment guides in its own coordinate space.
- **ViewDimensions3D**: A view’s 3D size and alignment guides in its own coordinate space.
- **SpatialContainer**: A layout container that aligns overlapping content in 3D space.

## Conforms To

- Equatable
- Sendable
- SendableMetatype

