---
来源： https://developer.apple.com/documentation/swiftui/geometryproxycoordinatespace3d
抓取时间： 2025-12-03T06:35:45Z
---

# 几何代理坐标空间 3D

**Structure**

表示`GeometryProxy3D`，可用于基于`CoordinateSpace3D`的转换。

### 声明

```swift
struct GeometryProxyCoordinateSpace3D
```

## 实例方法

- **anchored(in:)**：返回修改后的`CoordinateSpace3D`偏移量，以匹配原始坐标空间中提供的`anchorPoint`。

## 访问几何结构体

- **Axis**：二维坐标系中的水平或垂直维度。
- **Angle**：几何角度，其值可以用弧度或度表示。
- **UnitPoint**：视图坐标空间中的一个归一化二维点。
- **UnitPoint3D**：视图坐标空间中的一个归一化 3D 点。
- **Anchor**：从锚点来源和特定视图导出的不透明值。
- **DepthAlignmentID**：从锚点源和特定视图导出的不透明值。
- **Alignment3D**：三轴对齐。

## 符合

- 坐标空间 3D


---
source: https://developer.apple.com/documentation/swiftui/geometryproxycoordinatespace3d
crawled: 2025-12-03T06:35:45Z
---

# GeometryProxyCoordinateSpace3D

**Structure**

A representation of a `GeometryProxy3D` which can be used for `CoordinateSpace3D` based conversions.

## Declaration

```swift
struct GeometryProxyCoordinateSpace3D
```

## Instance Methods

- **anchored(in:)**: Returns a modified `CoordinateSpace3D` offset to match the provided `anchorPoint` in the original coordinate space.

## Accessing geometric constructs

- **Axis**: The horizontal or vertical dimension in a 2D coordinate system.
- **Angle**: A geometric angle whose value you access in either radians or degrees.
- **UnitPoint**: A normalized 2D point in a view’s coordinate space.
- **UnitPoint3D**: A normalized 3D point in a view’s coordinate space.
- **Anchor**: An opaque value derived from an anchor source and a particular view.
- **DepthAlignmentID**
- **Alignment3D**: An alignment in all three axes.

## Conforms To

- CoordinateSpace3D

