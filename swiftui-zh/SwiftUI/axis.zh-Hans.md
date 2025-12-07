---
来源： https://developer.apple.com/documentation/swiftui/axis
抓取时间： 2025-12-03T06:35:40Z
---

# 轴

**Enumeration**

二维坐标系中的水平或垂直维度。

## 声明

```swift
@frozen enum Axis
```

## 获取坐标轴

- **Axis.horizontal**：水平维度。
- **Axis.vertical**：垂直尺寸。

## 获取所有坐标轴

- **Axis.Set**：一组有效的坐标轴。

## 访问几何结构

- **Angle**：一个几何角度，其值可以用弧度或度来表示。
- **UnitPoint**：视图坐标空间中的一个归一化二维点。
- **UnitPoint3D**：视图坐标空间中的一个归一化 3D 点。
- **Anchor**：从锚点来源和特定视图导出的不透明值。
- **DepthAlignmentID**：从锚点源和特定视图导出的不透明值。
- **Alignment3D**：三个轴都对齐。
- **GeometryProxyCoordinateSpace3D**：`GeometryProxy3D`的表示，可用于基于`CoordinateSpace3D`的转换。

## 符合

- 比特可复制
- CaseIterable
- 可复制
- 自定义字符串可转换
- 等价
- 可散列
- 原始可表示
- 可发送
- 可发送元类型


---
source: https://developer.apple.com/documentation/swiftui/axis
crawled: 2025-12-03T06:35:40Z
---

# Axis

**Enumeration**

The horizontal or vertical dimension in a 2D coordinate system.

## Declaration

```swift
@frozen enum Axis
```

## Getting axes

- **Axis.horizontal**: The horizontal dimension.
- **Axis.vertical**: The vertical dimension.

## Getting all axes

- **Axis.Set**: An efficient set of axes.

## Accessing geometric constructs

- **Angle**: A geometric angle whose value you access in either radians or degrees.
- **UnitPoint**: A normalized 2D point in a view’s coordinate space.
- **UnitPoint3D**: A normalized 3D point in a view’s coordinate space.
- **Anchor**: An opaque value derived from an anchor source and a particular view.
- **DepthAlignmentID**
- **Alignment3D**: An alignment in all three axes.
- **GeometryProxyCoordinateSpace3D**: A representation of a `GeometryProxy3D` which can be used for `CoordinateSpace3D` based conversions.

## Conforms To

- BitwiseCopyable
- CaseIterable
- Copyable
- CustomStringConvertible
- Equatable
- Hashable
- RawRepresentable
- Sendable
- SendableMetatype

