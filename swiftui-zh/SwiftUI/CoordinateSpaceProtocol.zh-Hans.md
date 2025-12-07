---
来源： https://developer.apple.com/documentation/SwiftUI/CoordinateSpaceProtocol
抓取时间： 2025-12-02T17:37:45Z
---

# 坐标空间协议

**Protocol**

布局系统中的参照基准。

## 声明

```swift
protocol CoordinateSpaceProtocol
```

## 概览

视图的所有几何属性，包括大小、位置和变换，都是在视图父节点的本地坐标空间中定义的。通过向`GeometryProxy.frame(in:)`等函数传递符合本协议的类型，可以将这些值转换到其他坐标空间。

例如，命名坐标空间允许您通过使用`coordinateSpace(_:)`修饰符定义命名坐标空间，然后将相同的命名坐标空间传递到`frame(in:)`函数，从而将视图的框架转换为父级视图的本地坐标空间。

```swift
VStack {
    GeometryReader { geometryProxy in
        let distanceFromTop = geometryProxy.frame(in: "container").origin.y
        Text("This view is \(distanceFromTop) points from the top of the VStack")
    }
    .padding()
}
.coordinateSpace(.named("container"))
```

您通常不会自己创建符合该协议的类型。相反，请使用系统提供的 `.global`、`.local` 和 `.named(_:)` 实现。

## 获取内置坐标空间

- **immersiveSpace**：已命名的坐标空间，代表当前打开的[ImmersiveSpace](ImmersiveSpace.zh-Hans.md) 场景。如果当前没有打开沉浸式空间，该坐标空间将提供与 `.global` 坐标空间相同的行为。
- **global**：位于视图层次结构根部的全局坐标空间。
- **local**：当前视图的局部坐标空间。
- **named(_:)**：当前视图的局部坐标空间：使用给定值创建命名坐标空间。
- **scrollView**：系统为包含滚动视图的最内层添加的已命名坐标空间。
- **scrollView(axis:)**：系统为包含滚动视图的最内层添加的已命名坐标空间，允许沿提供的轴滚动。

## 获取已解析的坐标空间

- **coordinateSpace**：已解析的坐标空间。

## 支持类型

- **GlobalCoordinateSpace**：位于视图层次结构根部的全局坐标空间。
- **LocalCoordinateSpace**：当前视图的局部坐标空间。
- **NamedCoordinateSpace**：已命名的坐标空间。

## 测量视图

- **GeometryReader**：容器视图，将其内容定义为自身大小和坐标空间的函数。
- **GeometryReader3D**：将其内容定义为其自身大小和坐标空间函数的容器视图。
- **GeometryProxy**：用于访问容器视图的大小和坐标空间（锚点分辨率）的代理。
- **GeometryProxy3D**：用于访问容器视图的大小和坐标空间的代理。
- **coordinateSpace(_:)**：为视图的坐标空间指定一个名称，这样其他代码就可以对相对于命名空间的点和尺寸等维度进行操作。
- **CoordinateSpace**：由坐标空间协议创建的已解析坐标空间。
- **PhysicalMetric**：以点为单位提供与指定物理测量值相对应的访问。
- **PhysicalMetricsConverter**：物理度量转换器以物理长度度量的形式，提供点值与其在三维空间中的范围之间的转换。

## 符合类型

- 全局坐标空间
- 局部坐标空间
- 命名坐标空间


---
source: https://developer.apple.com/documentation/SwiftUI/CoordinateSpaceProtocol
crawled: 2025-12-02T17:37:45Z
---

# CoordinateSpaceProtocol

**Protocol**

A frame of reference within the layout system.

## Declaration

```swift
protocol CoordinateSpaceProtocol
```

## Overview

All geometric properties of a view, including size, position, and transform, are defined within the local coordinate space of the view’s parent. These values can be converted into other coordinate spaces by passing types conforming to this protocol into functions such as `GeometryProxy.frame(in:)`.

For example, a named coordinate space allows you to convert the frame of a view into the local coordinate space of an ancestor view by defining a named coordinate space using the `coordinateSpace(_:)` modifier, then passing that same named coordinate space into the `frame(in:)` function.

```swift
VStack {
    GeometryReader { geometryProxy in
        let distanceFromTop = geometryProxy.frame(in: "container").origin.y
        Text("This view is \(distanceFromTop) points from the top of the VStack")
    }
    .padding()
}
.coordinateSpace(.named("container"))
```

You don’t typically create types conforming to this protocol yourself. Instead, use the system-provided `.global`, `.local`, and `.named(_:)` implementations.

## Getting built-in coordinate spaces

- **immersiveSpace**: The named coordinate space that represents the currently opened [ImmersiveSpace](ImmersiveSpace.zh-Hans.md) scene. If no immersive space is currently opened, this CoordinateSpace provides the same behavior as the `.global` coordinate space.
- **global**: The global coordinate space at the root of the view hierarchy.
- **local**: The local coordinate space of the current view.
- **named(_:)**: Creates a named coordinate space using the given value.
- **scrollView**: The named coordinate space that is added by the system for the innermost containing scroll view.
- **scrollView(axis:)**: The named coordinate space that is added by the system for the innermost containing scroll view that allows scrolling along the provided axis.

## Getting the resolved coordinate space

- **coordinateSpace**: The resolved coordinate space.

## Supporting types

- **GlobalCoordinateSpace**: The global coordinate space at the root of the view hierarchy.
- **LocalCoordinateSpace**: The local coordinate space of the current view.
- **NamedCoordinateSpace**: A named coordinate space.

## Measuring a view

- **GeometryReader**: A container view that defines its content as a function of its own size and coordinate space.
- **GeometryReader3D**: A container view that defines its content as a function of its own size and coordinate space.
- **GeometryProxy**: A proxy for access to the size and coordinate space (for anchor resolution) of the container view.
- **GeometryProxy3D**: A proxy for access to the size and coordinate space of the container view.
- **coordinateSpace(_:)**: Assigns a name to the view’s coordinate space, so other code can operate on dimensions like points and sizes relative to the named space.
- **CoordinateSpace**: A resolved coordinate space created by the coordinate space protocol.
- **PhysicalMetric**: Provides access to a value in points that corresponds to the specified physical measurement.
- **PhysicalMetricsConverter**: A physical metrics converter provides conversion between point values and their extent in 3D space, in the form of physical length measurements.

## Conforming Types

- GlobalCoordinateSpace
- LocalCoordinateSpace
- NamedCoordinateSpace

