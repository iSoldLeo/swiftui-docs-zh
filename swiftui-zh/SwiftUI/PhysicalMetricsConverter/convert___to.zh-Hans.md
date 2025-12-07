--- 来源：https://developer.apple.com/documentation/SwiftUI/PhysicalMetricsConverter/convert(_:to:)

抓取时间：2025-12-01T11:23:04Z

---

# convert(_:to:)

**实例方法**

将点的坐标转换为指定单位的物理长度。

## 声明

```swift
@MainActor @preconcurrency func convert(_ point: CGPoint, to unit: UnitLength) -> CGPoint
```

## 返回值

以给定单位表示的点的物理长度值

## 说明

假定该点位于此转换器关联的场景的坐标系中。如果场景已缩放，则物理长度将考虑此缩放比例。

## 转换单位长度

- **convert(_:from:)**：将指定单位的长度转换为适用于此转换器关联环境的点长度。


---
source: https://developer.apple.com/documentation/SwiftUI/PhysicalMetricsConverter/convert(_:to:)
crawled: 2025-12-01T11:23:04Z
---

# convert(_:to:)

**Instance Method**

Converts a point’s coordinates to physical length measurements in the specified unit.

## Declaration

```swift
@MainActor @preconcurrency func convert(_ point: CGPoint, to unit: UnitLength) -> CGPoint
```

## Return Value

A point value with physical length measurements, in the given unit

## Discussion

The point is assumed to be in the coordinate system of the scene that this converter is associated with. If the scene is scaled, the physical measurement will take this scale into account.

## Converting a unit length

- **convert(_:from:)**: Converts a length in the specified unit to a length in points suitable for use in the environment this converter is associated with.

