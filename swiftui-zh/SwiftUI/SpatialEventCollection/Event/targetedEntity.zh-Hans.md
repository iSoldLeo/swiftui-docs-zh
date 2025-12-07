---
来源： https://developer.apple.com/documentation/SwiftUI/SpatialEventCollection/Event/targetedEntity
抓取时间： 2025-12-04T13:37:52Z
---

# 目标实体

**实例属性**

此触摸的目标实体（如果存在）。

## 声明

```swift
var targetedEntity: Entity?
```

## 定位事件

- **location**：事件的 2D 位置。
- **location3D**：触摸的 3D 位置。
- **selectionRay**：用于定位触摸的 3D 射线。
- **inputDevicePose**：控制触摸的设备的 3D 位置和方向（如果存在）。
- **SpatialEventCollection.Event.InputDevicePose**：描述输入设备（如控制事件的手）的姿势。


---
source: https://developer.apple.com/documentation/SwiftUI/SpatialEventCollection/Event/targetedEntity
crawled: 2025-12-04T13:37:52Z
---

# targetedEntity

**Instance Property**

The entity target for this touch, if one exists.

## Declaration

```swift
var targetedEntity: Entity?
```

## Locating the event

- **location**: The 2D location of the event.
- **location3D**: The 3D location of the touch.
- **selectionRay**: The 3D ray used to target the touch.
- **inputDevicePose**: The 3D position and orientation of the device controlling the touch, if one exists.
- **SpatialEventCollection.Event.InputDevicePose**: A pose describing the input device like a hand controlling the event.

