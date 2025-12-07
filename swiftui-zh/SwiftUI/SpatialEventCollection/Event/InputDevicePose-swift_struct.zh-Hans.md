---
来源： https://developer.apple.com/documentation/SwiftUI/SpatialEventCollection/Event/InputDevicePose-swift.struct
抓取时间： 2025-12-04T13:37:51Z
---

# SpatialEventCollection.Event.InputDevicePose

**Structure**

描述输入设备（如控制事件的手）的姿势。

## 声明

```swift
struct InputDevicePose
```

## 获取事件类型

- **altitude**：高度角。
- **azimuth**：方位角。
- **pose3D**：输入设备的 3D 姿态。

## 定位事件

- **location**：事件的 2D 位置。
- **location3D**：触摸的 3D 位置。
- **selectionRay**：用于定位触摸的 3D 射线。
- **inputDevicePose**：控制触摸的设备的 3D 位置和方向（如果存在）。
- **targetedEntity**：该触摸的实体目标（如果存在）。

## 符合

- 等价
- 可散列


---
source: https://developer.apple.com/documentation/SwiftUI/SpatialEventCollection/Event/InputDevicePose-swift.struct
crawled: 2025-12-04T13:37:51Z
---

# SpatialEventCollection.Event.InputDevicePose

**Structure**

A pose describing the input device like a hand controlling the event.

## Declaration

```swift
struct InputDevicePose
```

## Getting the event type

- **altitude**: The altitude angle.
- **azimuth**: The azimuth angle.
- **pose3D**: The 3D pose of the input device.

## Locating the event

- **location**: The 2D location of the event.
- **location3D**: The 3D location of the touch.
- **selectionRay**: The 3D ray used to target the touch.
- **inputDevicePose**: The 3D position and orientation of the device controlling the touch, if one exists.
- **targetedEntity**: The entity target for this touch, if one exists.

## Conforms To

- Equatable
- Hashable

