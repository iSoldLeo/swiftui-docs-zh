--- 来源：https://developer.apple.com/documentation/swiftui/geometryproxy3d
抓取时间：2025-12-03T19:22:21Z

---

# GeometryProxy3D

**Structure**

用于访问容器视图的大小和坐标空间的代理。

## 声明

```swift
struct GeometryProxy3D
```

## 概述

您可以使用代理进行锚点解析。

## 访问几何特征

- **frame(in:)**：容器视图的边界矩形转换为已定义的坐标空间。

- **size**：容器视图的大小。

- **safeAreaInsets**：容器视图的安全区域内边距。

- **subscript(_:)**：解析容器视图的锚点值。

- **transform(in:)**：将容器视图的 3D 变换转换为指定的坐标空间。

## 实例方法

- **coordinateSpace3D(for:)**：返回一个可用于基于 `CoordinateSpace3D` 的坐标转换的值。

## 测量视图

- **GeometryReader**：一个容器视图，其内容根据自身大小和坐标空间进行定义。

- **GeometryReader3D**：一个容器视图，其内容根据自身大小和坐标空间进行定义。

- **GeometryProxy**：用于访问容器视图的大小和坐标空间（用于锚点解析）的代理。

- **coordinateSpace(_:)**：为视图的坐标空间指定一个名称，以便其他代码可以相对于该命名空间操作点和尺寸等尺寸。

- **CoordinateSpace**：由坐标空间协议创建的已解析坐标空间。

- **CoordinateSpaceProtocol**：布局系统中的参考系。

- **PhysicalMetric**：提供对与指定物理测量值对应的点值的访问。

- **PhysicalMetricsConverter**：物理度量转换器提供点值与其在三维空间中的范围（以物理长度测量值的形式）之间的转换。


---
source: https://developer.apple.com/documentation/swiftui/geometryproxy3d
crawled: 2025-12-03T19:22:21Z
---

# GeometryProxy3D

**Structure**

A proxy for access to the size and coordinate space of the container view.

## Declaration

```swift
struct GeometryProxy3D
```

## Overview

You can use a proxy for anchor resolution.

## Accessing geometry characteristics

- **frame(in:)**: The container view’s bounds rectangle converted to a defined coordinate space.
- **size**: The size of the container view.
- **safeAreaInsets**: The safe area inset of the container view.
- **subscript(_:)**: Resolves the value of an anchor to the container view.
- **transform(in:)**: The container view’s 3D transform converted to a defined coordinate space.

## Instance Methods

- **coordinateSpace3D(for:)**: Returns a value that can be used for `CoordinateSpace3D` based coordinate conversions.

## Measuring a view

- **GeometryReader**: A container view that defines its content as a function of its own size and coordinate space.
- **GeometryReader3D**: A container view that defines its content as a function of its own size and coordinate space.
- **GeometryProxy**: A proxy for access to the size and coordinate space (for anchor resolution) of the container view.
- **coordinateSpace(_:)**: Assigns a name to the view’s coordinate space, so other code can operate on dimensions like points and sizes relative to the named space.
- **CoordinateSpace**: A resolved coordinate space created by the coordinate space protocol.
- **CoordinateSpaceProtocol**: A frame of reference within the layout system.
- **PhysicalMetric**: Provides access to a value in points that corresponds to the specified physical measurement.
- **PhysicalMetricsConverter**: A physical metrics converter provides conversion between point values and their extent in 3D space, in the form of physical length measurements.

