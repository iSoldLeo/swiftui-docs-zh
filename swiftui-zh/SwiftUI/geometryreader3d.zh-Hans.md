---
来源： https://developer.apple.com/documentation/swiftui/geometryreader3d
抓取时间： 2025-12-03T19:22:20Z
---

# GeometryReader3D

**Structure**

一种容器视图，它将其内容定义为自身尺寸和坐标空间的函数。

## 声明

```swift
@frozen struct GeometryReader3D<Content> where Content : View
```

## 概览

该视图可将灵活的首选尺寸返回给自己的容器视图。

此容器与 [GeometryReader](GeometryReader.zh-Hans.md) 的不同之处在于它也读取可用深度，因此也会向其父布局返回灵活的首选深度。只有在需要读取深度的情况下才使用 3D 版本，因为它在类似[ZStack](ZStack.zh-Hans.md) 的容器中使用时会影响深度布局。

## 创建几何体读取器

- **init(content:)**
- **content**

## 测量视图

- **GeometryReader**：容器视图，将其内容定义为自身大小和坐标空间的函数。
- **GeometryProxy**：用于访问容器视图的大小和坐标空间（锚点分辨率）的代理。
- **GeometryProxy3D**：用于访问容器视图的大小和坐标空间的代理。
- **coordinateSpace(_:)**：为视图的坐标空间指定一个名称，以便其他代码可以对相对于命名空间的点和尺寸等维度进行操作。
- **CoordinateSpace**：由坐标空间协议创建的已解析坐标空间。
- **CoordinateSpaceProtocol**：布局系统中的参照基准。
- **PhysicalMetric**：以点为单位访问与指定物理测量值相对应的值。
- **PhysicalMetricsConverter**：物理度量转换器以物理长度度量的形式，提供点值与其在三维空间中的范围之间的转换。

## 符合

- 查看


---
source: https://developer.apple.com/documentation/swiftui/geometryreader3d
crawled: 2025-12-03T19:22:20Z
---

# GeometryReader3D

**Structure**

A container view that defines its content as a function of its own size and coordinate space.

## Declaration

```swift
@frozen struct GeometryReader3D<Content> where Content : View
```

## Overview

This view returns a flexible preferred size to its own container view.

This container differs from [GeometryReader](GeometryReader.zh-Hans.md) in that it also reads available depth, and thus also returns a flexible preferred depth to its parent layout. Use the 3D version only in situations where you need to read depth, because it affects depth layout when used in a container like a [ZStack](ZStack.zh-Hans.md).

## Creating a geometry reader

- **init(content:)**
- **content**

## Measuring a view

- **GeometryReader**: A container view that defines its content as a function of its own size and coordinate space.
- **GeometryProxy**: A proxy for access to the size and coordinate space (for anchor resolution) of the container view.
- **GeometryProxy3D**: A proxy for access to the size and coordinate space of the container view.
- **coordinateSpace(_:)**: Assigns a name to the view’s coordinate space, so other code can operate on dimensions like points and sizes relative to the named space.
- **CoordinateSpace**: A resolved coordinate space created by the coordinate space protocol.
- **CoordinateSpaceProtocol**: A frame of reference within the layout system.
- **PhysicalMetric**: Provides access to a value in points that corresponds to the specified physical measurement.
- **PhysicalMetricsConverter**: A physical metrics converter provides conversion between point values and their extent in 3D space, in the form of physical length measurements.

## Conforms To

- View

