---
来源： https://developer.apple.com/documentation/SwiftUI/PencilSqueezeGesturePhase
抓取时间： 2025-12-02T17:41:09Z
---

# PencilSqueezeGesturePhase

**Enumeration**

描述 Apple Pencil 挤压手势的阶段和值。

## 声明

```swift
@frozen enum PencilSqueezeGesturePhase
```

## 概览

使用[onPencilSqueeze(perform:)](View/onPencilSqueeze_perform.zh-Hans.md) 视图修改器时，可以在`action` 闭合中处理 Apple Pencil 挤压手势的阶段。

## 枚举案例

- **PencilSqueezeGesturePhase.active(_:)**：用户开始挤压 Apple Pencil。
- **PencilSqueezeGesturePhase.ended(_:)**：用户成功完成挤压手势。
- **PencilSqueezeGesturePhase.failed**：用户开始挤压 Apple Pencil，但未能成功完成手势。

## 识别 Apple Pencil 手势

- **onPencilDoubleTap(perform:)**：在用户双击 Apple Pencil 后添加要执行的操作。
- **onPencilSqueeze(perform:)**：添加用户挤压 Apple Pencil 时要执行的操作。
- **preferredPencilDoubleTapAction**：用户喜欢在双击 Apple Pencil 后执行的操作，如在设置 app 中所选。
- **preferredPencilSqueezeAction**：用户在设置 app 中选择的挤压 Apple Pencil 时喜欢执行的操作。
- **PencilPreferredAction**：用户喜欢在双击 Apple Pencil 后执行的操作。
- **PencilDoubleTapGestureValue**：描述 Apple Pencil 双击手势的值。
- **PencilSqueezeGestureValue**：描述 Apple Pencil 挤压手势的值。
- **PencilHoverPose**：描述 Apple Pencil 挤压手势的值：描述 Apple Pencil 在视图边界上方区域悬停的位置和距离的值。

## 符合

- 等价


---
source: https://developer.apple.com/documentation/SwiftUI/PencilSqueezeGesturePhase
crawled: 2025-12-02T17:41:09Z
---

# PencilSqueezeGesturePhase

**Enumeration**

Describes the phase and value of an Apple Pencil squeeze gesture.

## Declaration

```swift
@frozen enum PencilSqueezeGesturePhase
```

## Overview

When you use the [onPencilSqueeze(perform:)](View/onPencilSqueeze_perform.zh-Hans.md) view modifier, you can handle the Apple Pencil squeeze gesture’s phase in the `action` closure.

## Enumeration Cases

- **PencilSqueezeGesturePhase.active(_:)**: The user started squeezing their Apple Pencil.
- **PencilSqueezeGesturePhase.ended(_:)**: The user successfully completed a squeeze gesture.
- **PencilSqueezeGesturePhase.failed**: The user started squeezing their Apple Pencil but failed to successfully complete the gesture.

## Recognizing Apple Pencil gestures

- **onPencilDoubleTap(perform:)**: Adds an action to perform after the user double-taps their Apple Pencil.
- **onPencilSqueeze(perform:)**: Adds an action to perform when the user squeezes their Apple Pencil.
- **preferredPencilDoubleTapAction**: The action that the user prefers to perform after double-tapping their Apple Pencil, as selected in the Settings app.
- **preferredPencilSqueezeAction**: The action that the user prefers to perform when squeezing their Apple Pencil, as selected in the Settings app.
- **PencilPreferredAction**: An action that the user prefers to perform after double-tapping their Apple Pencil.
- **PencilDoubleTapGestureValue**: Describes the value of an Apple Pencil double-tap gesture.
- **PencilSqueezeGestureValue**: Describes the value of an Apple Pencil squeeze gesture.
- **PencilHoverPose**: A value describing the location and distance of an Apple Pencil hovering in the area above a view’s bounds.

## Conforms To

- Equatable

