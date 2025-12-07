--- 来源：https://developer.apple.com/documentation/swiftui/geometryreader
抓取时间：2025-12-04T11:34:19Z

---

# GeometryReader

**Structure**

一个容器视图，其内容根据自身大小和坐标空间进行定义。

## 声明

```swift
@frozen struct GeometryReader<Content> where Content : View
```

## 概述

此视图会向其父布局返回一个灵活的首选大小。

## 创建几何体读取器

- **init(content:)**

- **content**

## 测量视图

- **GeometryReader3D**：一个容器视图，其内容根据自身大小和坐标空间进行定义。

- **GeometryProxy**：用于访问容器视图的大小和坐标空间（用于锚点解析）的代理。

- **GeometryProxy3D**：用于访问容器视图的大小和坐标空间的代理。

- **coordinateSpace(_:)**：为视图的坐标空间指定一个名称，以便其他代码可以相对于该命名空间操作点和尺寸等维度。

- **CoordinateSpace**：由坐标空间协议创建的已解析坐标空间。

- **CoordinateSpaceProtocol**：布局系统中的参考系。

- **PhysicalMetric**：提供对与指定物理测量值对应的点值的访问。

- **PhysicalMetricsConverter**：物理度量转换器提供点值与其在三维空间中的范围（以物理长度测量值的形式）之间的转换。

## 符合

- 查看


---
source: https://developer.apple.com/documentation/swiftui/geometryreader
crawled: 2025-12-04T11:34:19Z
---

# GeometryReader

**Structure**

A container view that defines its content as a function of its own size and coordinate space.

## Declaration

```swift
@frozen struct GeometryReader<Content> where Content : View
```

## Overview

This view returns a flexible preferred size to its parent layout.

## Creating a geometry reader

- **init(content:)**
- **content**

## Measuring a view

- **GeometryReader3D**: A container view that defines its content as a function of its own size and coordinate space.
- **GeometryProxy**: A proxy for access to the size and coordinate space (for anchor resolution) of the container view.
- **GeometryProxy3D**: A proxy for access to the size and coordinate space of the container view.
- **coordinateSpace(_:)**: Assigns a name to the view’s coordinate space, so other code can operate on dimensions like points and sizes relative to the named space.
- **CoordinateSpace**: A resolved coordinate space created by the coordinate space protocol.
- **CoordinateSpaceProtocol**: A frame of reference within the layout system.
- **PhysicalMetric**: Provides access to a value in points that corresponds to the specified physical measurement.
- **PhysicalMetricsConverter**: A physical metrics converter provides conversion between point values and their extent in 3D space, in the form of physical length measurements.

## Conforms To

- View

