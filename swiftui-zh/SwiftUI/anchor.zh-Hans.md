---
来源： https://developer.apple.com/documentation/swiftui/anchor
抓取时间： 2025-12-03T06:35:43Z
---

# 锚点

**Structure**

从锚点来源和特定视图导出的不透明值。

## 声明

```swift
@frozen struct Anchor<Value>
```

## 概览

您可以使用[GeometryProxy](GeometryProxy.zh-Hans.md) 指定目标视图，将锚点转换为目标视图坐标空间中的`Value`。

## 获取锚点的来源

- **Anchor.Source**：一个经过类型擦除的几何图形值，它可以产生一个给定类型的锚点值。

## 访问几何结构体

- **Axis**：二维坐标系中的水平或垂直尺寸。
- **Angle**：几何角度，其值可以用弧度或度表示。
- **UnitPoint**：视图坐标空间中的一个归一化二维点。
- **UnitPoint3D**：视图坐标空间中的一个归一化 3D 点。
- **DepthAlignmentID**：视图坐标空间中的归一化三维点。
- **Alignment3D**：三个轴都对齐。
- **GeometryProxyCoordinateSpace3D**：`GeometryProxy3D`的表示，可用于基于`CoordinateSpace3D`的转换。

## 符合

- 坐标空间值 3D
- 可复制
- 等价
- 可散列
- 可发送
- 可发送元类型


---
source: https://developer.apple.com/documentation/swiftui/anchor
crawled: 2025-12-03T06:35:43Z
---

# Anchor

**Structure**

An opaque value derived from an anchor source and a particular view.

## Declaration

```swift
@frozen struct Anchor<Value>
```

## Overview

You can convert the anchor to a `Value` in the coordinate space of a target view by using a [GeometryProxy](GeometryProxy.zh-Hans.md) to specify the target view.

## Getting the anchor’s source

- **Anchor.Source**: A type-erased geometry value that produces an anchored value of a given type.

## Accessing geometric constructs

- **Axis**: The horizontal or vertical dimension in a 2D coordinate system.
- **Angle**: A geometric angle whose value you access in either radians or degrees.
- **UnitPoint**: A normalized 2D point in a view’s coordinate space.
- **UnitPoint3D**: A normalized 3D point in a view’s coordinate space.
- **DepthAlignmentID**
- **Alignment3D**: An alignment in all three axes.
- **GeometryProxyCoordinateSpace3D**: A representation of a `GeometryProxy3D` which can be used for `CoordinateSpace3D` based conversions.

## Conforms To

- CoordinateSpaceValue3D
- Copyable
- Equatable
- Hashable
- Sendable
- SendableMetatype

