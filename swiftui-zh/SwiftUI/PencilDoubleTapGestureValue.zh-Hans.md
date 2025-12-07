---
来源： https://developer.apple.com/documentation/SwiftUI/PencilDoubleTapGestureValue
抓取时间： 2025-12-02T17:41:08Z
---

# PencilDoubleTapGestureValue

**Structure**

描述 Apple Pencil 双击手势的值。

## 声明

```swift
struct PencilDoubleTapGestureValue
```

## 获取手势值

- **hoverPose**：双击手势发生时，悬停在视图边界上方区域的 Apple Pencil 的位置和距离。

## 识别 Apple Pencil 手势

- **onPencilDoubleTap(perform:)**：在用户双击 Apple Pencil 后添加要执行的操作。
- **onPencilSqueeze(perform:)**：添加用户挤压 Apple Pencil 时要执行的操作。
- **preferredPencilDoubleTapAction**：用户喜欢在双击 Apple Pencil 后执行的操作，如在设置 app 中所选。
- **preferredPencilSqueezeAction**：用户在设置 app 中选择的挤压 Apple Pencil 时喜欢执行的操作。
- **PencilPreferredAction**：用户喜欢在双击 Apple Pencil 后执行的操作。
- **PencilSqueezeGestureValue**：描述 Apple Pencil 挤压手势的值。
- **PencilSqueezeGesturePhase**：描述 Apple Pencil 挤压手势的相位和值。
- **PencilHoverPose**：描述 Apple Pencil 在视图边界上方区域悬停的位置和距离的值。

## 符合

- 等价
- 哈希值


---
source: https://developer.apple.com/documentation/SwiftUI/PencilDoubleTapGestureValue
crawled: 2025-12-02T17:41:08Z
---

# PencilDoubleTapGestureValue

**Structure**

Describes the value of an Apple Pencil double-tap gesture.

## Declaration

```swift
struct PencilDoubleTapGestureValue
```

## Getting the gesture values

- **hoverPose**: The location and distance of an Apple Pencil hovering in the area above the view’s bounds when the double-tap gesture occurred.

## Recognizing Apple Pencil gestures

- **onPencilDoubleTap(perform:)**: Adds an action to perform after the user double-taps their Apple Pencil.
- **onPencilSqueeze(perform:)**: Adds an action to perform when the user squeezes their Apple Pencil.
- **preferredPencilDoubleTapAction**: The action that the user prefers to perform after double-tapping their Apple Pencil, as selected in the Settings app.
- **preferredPencilSqueezeAction**: The action that the user prefers to perform when squeezing their Apple Pencil, as selected in the Settings app.
- **PencilPreferredAction**: An action that the user prefers to perform after double-tapping their Apple Pencil.
- **PencilSqueezeGestureValue**: Describes the value of an Apple Pencil squeeze gesture.
- **PencilSqueezeGesturePhase**: Describes the phase and value of an Apple Pencil squeeze gesture.
- **PencilHoverPose**: A value describing the location and distance of an Apple Pencil hovering in the area above a view’s bounds.

## Conforms To

- Equatable
- Hashable

