--- 来源：https://developer.apple.com/documentation/swiftui/coordinatespace

抓取时间：2025-12-04T13:28:50Z

---

# 坐标空间

**Enumeration**

由坐标空间协议创建的已解析坐标空间。

## 声明

```swift
enum CoordinateSpace
```

## 概述

通常情况下，您不会直接使用 `CoordinateSpace`。而是使用 `CoordinateSpaceProtocol` 的静态属性和函数，例如 `.global`、`.local` 和 `.named(_:)`。

## 获取坐标空间

- **CoordinateSpace.global**：视图层次结构根部的全局坐标空间。

- **CoordinateSpace.local**：当前视图的局部坐标空间。

- **CoordinateSpace.named(_:)**：指向视图局部坐标空间的命名引用。

## 测试空间

- **isGlobal**

- **isLocal**

## 测量视图

- **GeometryReader**：一个容器视图，其内容根据自身大小和坐标空间进行定义。

- **GeometryReader3D**：一个容器视图，其内容根据自身大小和坐标空间进行定义。

- **GeometryProxy**：用于访问容器视图的大小和坐标空间（用于锚点解析）的代理。

- **GeometryProxy3D**：用于访问容器视图的大小和坐标空间的代理。

- **coordinateSpace(_:)**：为视图的坐标空间指定一个名称，以便其他代码可以相对于该命名空间操作点和尺寸等维度。

- **CoordinateSpaceProtocol**：布局系统中的参考系。

- **PhysicalMetric**：提供对与指定物理测量值对应的点值的访问。

- **PhysicalMetricsConverter**：物理度量转换器提供点值与其在三维空间中的范围（以物理长度测量值的形式）之间的转换。

## 符合以下规范

- 可复制

- 可等值化

- 可哈希化


---
source: https://developer.apple.com/documentation/swiftui/coordinatespace
crawled: 2025-12-04T13:28:50Z
---

# CoordinateSpace

**Enumeration**

A resolved coordinate space created by the coordinate space protocol.

## Declaration

```swift
enum CoordinateSpace
```

## Overview

You don’t typically use `CoordinateSpace` directly. Instead, use the static properties and functions of `CoordinateSpaceProtocol` such as `.global`, `.local`, and `.named(_:)`.

## Getting coordinate spaces

- **CoordinateSpace.global**: The global coordinate space at the root of the view hierarchy.
- **CoordinateSpace.local**: The local coordinate space of the current view.
- **CoordinateSpace.named(_:)**: A named reference to a view’s local coordinate space.

## Testing a space

- **isGlobal**
- **isLocal**

## Measuring a view

- **GeometryReader**: A container view that defines its content as a function of its own size and coordinate space.
- **GeometryReader3D**: A container view that defines its content as a function of its own size and coordinate space.
- **GeometryProxy**: A proxy for access to the size and coordinate space (for anchor resolution) of the container view.
- **GeometryProxy3D**: A proxy for access to the size and coordinate space of the container view.
- **coordinateSpace(_:)**: Assigns a name to the view’s coordinate space, so other code can operate on dimensions like points and sizes relative to the named space.
- **CoordinateSpaceProtocol**: A frame of reference within the layout system.
- **PhysicalMetric**: Provides access to a value in points that corresponds to the specified physical measurement.
- **PhysicalMetricsConverter**: A physical metrics converter provides conversion between point values and their extent in 3D space, in the form of physical length measurements.

## Conforms To

- Copyable
- Equatable
- Hashable

