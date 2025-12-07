---
来源： https://developer.apple.com/documentation/SwiftUI/DragGesture/Value/translation3D
抓取时间： 2025-12-03T19:57:22Z
---

# translation3D

**实例属性**

拖动手势从 `startLocation3D` 到 `location3D`的平移值。

## 声明

```swift
var translation3D: Vector3D { get }
```

## 获取 3D 位置

- **startLocation3D**：拖动手势的 3D 起始位置。
- **location3D**：拖动手势的 3D 位置。
- **predictedEndLocation3D**：根据当前拖动速度，预测如果现在停止拖动，最终位置会在哪里。
- **predictedEndTranslation3D**：根据当前的拖曳速度，预测如果现在停止拖曳，最终的平移量。
- **startInputDevicePose3D**：驱动拖曳的设备的起始 3D 姿态（如果存在）。
- **inputDevicePose3D**：驱动拖曳的设备的三维姿态（如果存在）。


---
source: https://developer.apple.com/documentation/SwiftUI/DragGesture/Value/translation3D
crawled: 2025-12-03T19:57:22Z
---

# translation3D

**Instance Property**

The translation of the drag gesture from `startLocation3D` to `location3D`.

## Declaration

```swift
var translation3D: Vector3D { get }
```

## Getting 3D position

- **startLocation3D**: The 3D start location of the drag gesture.
- **location3D**: The 3D location of the drag gesture.
- **predictedEndLocation3D**: A prediction of where the final location would be if dragging stopped now, based on the current drag velocity.
- **predictedEndTranslation3D**: A prediction of what the final translation would be if dragging stopped now, based on the current drag velocity.
- **startInputDevicePose3D**: The starting 3D pose of the device driving the drag, if one exists.
- **inputDevicePose3D**: The 3D pose of the device driving the drag, if one exists.

