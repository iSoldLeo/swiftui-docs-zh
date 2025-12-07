---
来源： https://developer.apple.com/documentation/SwiftUI/SpatialEventCollection/Event/location3D
抓取时间： 2025-12-04T13:37:48Z
---

# location3D

**实例属性**

触摸的 3D 位置。

## 声明

```swift
var location3D: Point3D
```

## 定位事件

- **location**：事件的 2D 位置。
- **selectionRay**：用于定位触摸的 3D 射线。
- **inputDevicePose**：控制触摸的设备的 3D 位置和方向（如果存在）。
- **SpatialEventCollection.Event.InputDevicePose**：描述输入设备（如控制事件的手）的姿势。
- **targetedEntity**：这次触摸的实体目标（如果存在）。


---
source: https://developer.apple.com/documentation/SwiftUI/SpatialEventCollection/Event/location3D
crawled: 2025-12-04T13:37:48Z
---

# location3D

**Instance Property**

The 3D location of the touch.

## Declaration

```swift
var location3D: Point3D
```

## Locating the event

- **location**: The 2D location of the event.
- **selectionRay**: The 3D ray used to target the touch.
- **inputDevicePose**: The 3D position and orientation of the device controlling the touch, if one exists.
- **SpatialEventCollection.Event.InputDevicePose**: A pose describing the input device like a hand controlling the event.
- **targetedEntity**: The entity target for this touch, if one exists.

