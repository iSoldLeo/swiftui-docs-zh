---
来源： https://developer.apple.com/documentation/SwiftUI/SpatialEventCollection/Event/selectionRay
抓取时间： 2025-12-04T13:37:49Z
---

# 选择射线

**实例属性**

用于锁定触摸目标的三维射线。

## 声明

```swift
var selectionRay: Ray3D?
```

## 定位事件

- **location**：事件的 2D 位置。
- **location3D**：触摸的 3D 位置。
- **inputDevicePose**：控制触摸的设备的 3D 位置和方向（如果存在）。
- **SpatialEventCollection.Event.InputDevicePose**：描述输入设备（如控制事件的手）的姿势。
- **targetedEntity**：这次触摸的实体目标（如果存在）。


---
source: https://developer.apple.com/documentation/SwiftUI/SpatialEventCollection/Event/selectionRay
crawled: 2025-12-04T13:37:49Z
---

# selectionRay

**Instance Property**

The 3D ray used to target the touch.

## Declaration

```swift
var selectionRay: Ray3D?
```

## Locating the event

- **location**: The 2D location of the event.
- **location3D**: The 3D location of the touch.
- **inputDevicePose**: The 3D position and orientation of the device controlling the touch, if one exists.
- **SpatialEventCollection.Event.InputDevicePose**: A pose describing the input device like a hand controlling the event.
- **targetedEntity**: The entity target for this touch, if one exists.

