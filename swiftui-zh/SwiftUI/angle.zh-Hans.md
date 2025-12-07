--- 来源：https://developer.apple.com/documentation/swiftui/angle

抓取时间：2025-12-03T06:35:41Z

---

# 角度

**Structure**

一个几何角度，其值可以以弧度或角度表示。

## 声明

```swift
@frozen struct Angle
```

## 获取固定角度

- **zero**

- **degrees(_:)**

- **radians(_:)**

## 创建角度

- **init()**

- **init(degrees:)**

- **init(radians:)**

- **init(_:)**

## 获取角度大小

- **degrees**

- **radians**

## 访问几何构造

- **Axis**：二维坐标系中的水平或垂直尺寸。

- **UnitPoint**：视图坐标空间中的归一化二维点。

- **UnitPoint3D**：视图坐标空间中的归一化三维点。

- **Anchor**：从锚点源和特定视图派生的不透明值。

- **DepthAlignmentID**

- **Alignment3D**：所有三个轴上的对齐方式。

- **GeometryProxyCoordinateSpace3D**：`GeometryProxy3D` 的表示形式，可用于基于 `CoordinateSpace3D` 的转换。

## 符合以下规范

- 可动画化

- 可按位复制

- 可比较

- 可复制

- 可解码

- 可编码

- 可等值化

- 可哈希化

- 可发送

- 可发送元数据类型


---
source: https://developer.apple.com/documentation/swiftui/angle
crawled: 2025-12-03T06:35:41Z
---

# Angle

**Structure**

A geometric angle whose value you access in either radians or degrees.

## Declaration

```swift
@frozen struct Angle
```

## Getting constant angles

- **zero**
- **degrees(_:)**
- **radians(_:)**

## Creating an angle

- **init()**
- **init(degrees:)**
- **init(radians:)**
- **init(_:)**

## Getting the angle size

- **degrees**
- **radians**

## Accessing geometric constructs

- **Axis**: The horizontal or vertical dimension in a 2D coordinate system.
- **UnitPoint**: A normalized 2D point in a view’s coordinate space.
- **UnitPoint3D**: A normalized 3D point in a view’s coordinate space.
- **Anchor**: An opaque value derived from an anchor source and a particular view.
- **DepthAlignmentID**
- **Alignment3D**: An alignment in all three axes.
- **GeometryProxyCoordinateSpace3D**: A representation of a `GeometryProxy3D` which can be used for `CoordinateSpace3D` based conversions.

## Conforms To

- Animatable
- BitwiseCopyable
- Comparable
- Copyable
- Decodable
- Encodable
- Equatable
- Hashable
- Sendable
- SendableMetatype

