--- 来源：https://developer.apple.com/documentation/SwiftUI/MeshGradient/Locations-swift.enum

抓取时间：2025-12-03T05:43:08Z

---

# MeshGradient.Locations

**Enumeration**

一个包含二维位置及其控制点的数组。

## 声明

```swift
enum Locations
```

## 枚举情况

- **MeshGradient.Locations.bezierPoints(_:)**：显式指定位置和控制点的顶点。

- **MeshGradient.Locations.points(_:)**：仅指定位置的顶点，其控制点由相邻顶点的位置推断得出。

## 符合以下规范

- Equatable

- Sendable

- SendableMetatype


---
source: https://developer.apple.com/documentation/SwiftUI/MeshGradient/Locations-swift.enum
crawled: 2025-12-03T05:43:08Z
---

# MeshGradient.Locations

**Enumeration**

An array of 2D locations and their control points.

## Declaration

```swift
enum Locations
```

## Enumeration Cases

- **MeshGradient.Locations.bezierPoints(_:)**: Vertices explicitly specifying their location and control points.
- **MeshGradient.Locations.points(_:)**: Vertices are only specified as their location, their control points are inferred from the locations of their neighbors.

## Conforms To

- Equatable
- Sendable
- SendableMetatype

