--- 来源：https://developer.apple.com/documentation/SwiftUI/PencilSqueezeGestureValue
抓取时间：2025-12-02T17:41:08Z

---

# PencilSqueezeGestureValue

**Structure**

描述 Apple Pencil 挤压手势的值。

## 声明

```swift
struct PencilSqueezeGestureValue
```

## 实例属性

- **hoverPose**：挤压手势发生时，Apple Pencil 悬停在视图边界上方区域的位置和距离。

## 识别 Apple Pencil 手势

- **onPencilDoubleTap(perform:)**：添加用户双击 Apple Pencil 后要执行的操作。

- **onPencilSqueeze(perform:)**：添加用户挤压 Apple Pencil 时要执行的操作。

- **preferredPencilDoubleTapAction**：用户在“设置”应用中选择的，在双击 Apple Pencil 后首选执行的操作。

- **preferredPencilSqueezeAction**：用户在“设置”应用中选择的，在挤压 Apple Pencil 时首选执行的操作。

- **PencilPreferredAction**：用户在双击 Apple Pencil 后首选执行的操作。

- **PencilDoubleTapGestureValue**：描述 Apple Pencil 双击手势的值。

- **PencilSqueezeGesturePhase**：描述 Apple Pencil 挤压手势的阶段和值。

- **PencilHoverPose**：描述 Apple Pencil 在视图边界上方悬停时的位置和距离的值。

## 符合以下规范

- 可等值化

- 可哈希化


---
source: https://developer.apple.com/documentation/SwiftUI/PencilSqueezeGestureValue
crawled: 2025-12-02T17:41:08Z
---

# PencilSqueezeGestureValue

**Structure**

Describes the value of an Apple Pencil squeeze gesture.

## Declaration

```swift
struct PencilSqueezeGestureValue
```

## Instance Properties

- **hoverPose**: The location and distance of an Apple Pencil hovering in the area above the view’s bounds when the squeeze gesture occurred.

## Recognizing Apple Pencil gestures

- **onPencilDoubleTap(perform:)**: Adds an action to perform after the user double-taps their Apple Pencil.
- **onPencilSqueeze(perform:)**: Adds an action to perform when the user squeezes their Apple Pencil.
- **preferredPencilDoubleTapAction**: The action that the user prefers to perform after double-tapping their Apple Pencil, as selected in the Settings app.
- **preferredPencilSqueezeAction**: The action that the user prefers to perform when squeezing their Apple Pencil, as selected in the Settings app.
- **PencilPreferredAction**: An action that the user prefers to perform after double-tapping their Apple Pencil.
- **PencilDoubleTapGestureValue**: Describes the value of an Apple Pencil double-tap gesture.
- **PencilSqueezeGesturePhase**: Describes the phase and value of an Apple Pencil squeeze gesture.
- **PencilHoverPose**: A value describing the location and distance of an Apple Pencil hovering in the area above a view’s bounds.

## Conforms To

- Equatable
- Hashable

