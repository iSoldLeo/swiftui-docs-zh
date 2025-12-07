---
来源： https://developer.apple.com/documentation/SwiftUI/SpatialEventCollection/Event/location
抓取时间： 2025-12-04T13:37:48Z
---

# 位置

**实例属性**

事件的二维位置。

## 声明

```swift
var location: CGPoint
```

## 定位事件

- **location3D**：触摸的 3D 位置。
- **selectionRay**：用于定位触摸的 3D 射线。
- **inputDevicePose**：控制触摸的设备的 3D 位置和方向（如果存在）。
- **SpatialEventCollection.Event.InputDevicePose**：描述输入设备（如控制事件的手）的姿势。
- **targetedEntity**：本次触摸的实体目标（如果存在）。


---
source: https://developer.apple.com/documentation/SwiftUI/SpatialEventCollection/Event/location
crawled: 2025-12-04T13:37:48Z
---

# location

**Instance Property**

The 2D location of the event.

## Declaration

```swift
var location: CGPoint
```

## Locating the event

- **location3D**: The 3D location of the touch.
- **selectionRay**: The 3D ray used to target the touch.
- **inputDevicePose**: The 3D position and orientation of the device controlling the touch, if one exists.
- **SpatialEventCollection.Event.InputDevicePose**: A pose describing the input device like a hand controlling the event.
- **targetedEntity**: The entity target for this touch, if one exists.

