---
来源：https://developer.apple.com/documentation/SwiftUI/DragGesture/Value
抓取时间： 2025-12-02T21:47:13Z
---

# DragGesture.Value

**Structure**

拖动手势的属性。

## 声明

```swift
struct Value
```

## 获取二维位置

- **startLocation**：拖动手势第一个事件的位置。
- **location**：拖动手势当前事件的位置。
- **predictedEndLocation**：根据当前拖动速度，预测如果现在停止拖动，最终位置会在哪里。
- **translation**：从拖动手势开始到拖动手势当前事件之间的总平移量。
- **predictedEndTranslation**：根据当前拖动速度，预测如果现在停止拖动，最终的平移量。

## 获取 3D 位置

- **startLocation3D**：拖动手势的 3D 起始位置。
- **location3D**：拖动手势的 3D 位置。
- **predictedEndLocation3D**：根据当前拖动速度，预测如果现在停止拖动，最终位置会在哪里。
- **translation3D**：拖动手势从 `startLocation3D` 到 `location3D` 的平移。
- **predictedEndTranslation3D**：根据当前的拖曳速度，预测如果现在停止拖曳，最终的平移量。
- **startInputDevicePose3D**：驱动拖曳的设备的起始 3D 姿态（如果存在）。
- **inputDevicePose3D**：驱动拖曳的设备的三维姿态（如果存在）。

## 处理随时间发生的变化

- **time**：与拖动手势当前事件相关的时间。
- **velocity**：当前拖动速度。

## 符合

- 等价
- 可发送
- 可发送元数据类型


---
source: https://developer.apple.com/documentation/SwiftUI/DragGesture/Value
crawled: 2025-12-02T21:47:13Z
---

# DragGesture.Value

**Structure**

The attributes of a drag gesture.

## Declaration

```swift
struct Value
```

## Getting 2D position

- **startLocation**: The location of the drag gesture’s first event.
- **location**: The location of the drag gesture’s current event.
- **predictedEndLocation**: A prediction, based on the current drag velocity, of where the final location will be if dragging stopped now.
- **translation**: The total translation from the start of the drag gesture to the current event of the drag gesture.
- **predictedEndTranslation**: A prediction, based on the current drag velocity, of what the final translation will be if dragging stopped now.

## Getting 3D position

- **startLocation3D**: The 3D start location of the drag gesture.
- **location3D**: The 3D location of the drag gesture.
- **predictedEndLocation3D**: A prediction of where the final location would be if dragging stopped now, based on the current drag velocity.
- **translation3D**: The translation of the drag gesture from `startLocation3D` to `location3D`.
- **predictedEndTranslation3D**: A prediction of what the final translation would be if dragging stopped now, based on the current drag velocity.
- **startInputDevicePose3D**: The starting 3D pose of the device driving the drag, if one exists.
- **inputDevicePose3D**: The 3D pose of the device driving the drag, if one exists.

## Handling changes over time

- **time**: The time associated with the drag gesture’s current event.
- **velocity**: The current drag velocity.

## Conforms To

- Equatable
- Sendable
- SendableMetatype

