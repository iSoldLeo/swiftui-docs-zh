---
来源： https://developer.apple.com/documentation/SwiftUI/PencilHoverPose
抓取时间： 2025-12-02T17:41:10Z
---

# PencilHoverPose

**Structure**

描述 Apple Pencil 在视图边界上方区域悬停的位置和距离的值。

## 声明

```swift
struct PencilHoverPose
```

## 获取悬停特性

- **anchor**：Apple Pencil 在视图边界上方区域悬停时的位置，以相对于该视图的归一化锚点表示。
- **location**：Apple Pencil 在视图边界上方区域悬停时的位置，以该视图坐标空间中的一个点表示。
- **zDistance**：屏幕与悬停的 Apple Pencil 之间的归一化距离。

### 实例属性

- **altitude**：表示悬浮 Apple Pencil 高度角的值。
- **azimuth**：表示悬停 Apple Pencil 的方位角的数值。
- **roll**：表示悬停 Apple Pencil 的滚动角度的值。

## 识别 Apple Pencil 手势

- **onPencilDoubleTap(perform:)**：在用户双击 Apple Pencil 后添加一个要执行的操作。
- **onPencilSqueeze(perform:)**：添加用户挤压 Apple Pencil 时要执行的操作。
- **preferredPencilDoubleTapAction**：用户喜欢在双击 Apple Pencil 后执行的操作，如在设置 app 中所选。
- **preferredPencilSqueezeAction**：用户在设置 app 中选择的挤压 Apple Pencil 时喜欢执行的操作。
- **PencilPreferredAction**：用户喜欢在双击 Apple Pencil 后执行的操作。
- **PencilDoubleTapGestureValue**：描述 Apple Pencil 双击手势的值。
- **PencilSqueezeGestureValue**：描述 Apple Pencil 挤压手势的值。
- **PencilSqueezeGesturePhase**：描述 Apple Pencil 挤压手势的相位和值。

## 符合

- 等价
- 可散列


---
source: https://developer.apple.com/documentation/SwiftUI/PencilHoverPose
crawled: 2025-12-02T17:41:10Z
---

# PencilHoverPose

**Structure**

A value describing the location and distance of an Apple Pencil hovering in the area above a view’s bounds.

## Declaration

```swift
struct PencilHoverPose
```

## Getting the hover characteristics

- **anchor**: The location of an Apple Pencil hovering in the area above the view’s bounds, expressed as a normalized anchor point relative to that view.
- **location**: The location of an Apple Pencil hovering in the area above the view’s bounds, expressed as a point in that view’s coordinate space.
- **zDistance**: The normalized distance between the screen and a hovering Apple Pencil.

## Instance Properties

- **altitude**: A value that represents the altitude angle of the hovering Apple Pencil.
- **azimuth**: A value that represents the azimuth angle of a hovering Apple Pencil.
- **roll**: A value that represents the barrel roll angle of the hovering Apple Pencil.

## Recognizing Apple Pencil gestures

- **onPencilDoubleTap(perform:)**: Adds an action to perform after the user double-taps their Apple Pencil.
- **onPencilSqueeze(perform:)**: Adds an action to perform when the user squeezes their Apple Pencil.
- **preferredPencilDoubleTapAction**: The action that the user prefers to perform after double-tapping their Apple Pencil, as selected in the Settings app.
- **preferredPencilSqueezeAction**: The action that the user prefers to perform when squeezing their Apple Pencil, as selected in the Settings app.
- **PencilPreferredAction**: An action that the user prefers to perform after double-tapping their Apple Pencil.
- **PencilDoubleTapGestureValue**: Describes the value of an Apple Pencil double-tap gesture.
- **PencilSqueezeGestureValue**: Describes the value of an Apple Pencil squeeze gesture.
- **PencilSqueezeGesturePhase**: Describes the phase and value of an Apple Pencil squeeze gesture.

## Conforms To

- Equatable
- Hashable

