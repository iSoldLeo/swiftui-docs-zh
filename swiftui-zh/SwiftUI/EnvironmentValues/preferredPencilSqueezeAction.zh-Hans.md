---
来源： https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/preferredPencilSqueezeAction
抓取时间： 2025-12-02T17:41:06Z
---

# preferredPencilSqueezeAction

**实例属性**

用户在设置 app 中选择的挤压 Apple Pencil 时偏好执行的动作。

## 声明

```swift
var preferredPencilSqueezeAction: PencilPreferredAction { get }
```

## 讨论

您可以使用[Environment](../Environment.zh-Hans.md) 属性包装器创建一个属性，并在[onPencilSqueeze(perform:)](../View/onPencilSqueeze_perform.zh-Hans.md) 视图修饰符的动作闭包中使用该属性来读取该值，以指示当用户挤压 Apple Pencil 时要做什么：

```swift
@Environment(\.preferredPencilSqueezeAction) private var preferredAction

var body: some View {
    MyDrawingCanvas()
        .onPencilSqueeze { phase in
            switch (phase, preferredAction) {
                ...
            }
        }
}
```

在 macOS 中，用户无法更改该值，并始终将其设置为 [showContextualPalette](../PencilPreferredAction/showContextualPalette.zh-Hans.md)。

## 识别 Apple Pencil 手势

- **onPencilDoubleTap(perform:)**：在用户双击 Apple Pencil 后添加一个要执行的操作。
- **onPencilSqueeze(perform:)**：添加用户挤压 Apple Pencil 时要执行的操作。
- **preferredPencilDoubleTapAction**：用户希望在双击 Apple Pencil 后执行的操作，如在设置 app 中所选。
- **PencilPreferredAction**：用户喜欢在双击 Apple Pencil 后执行的操作。
- **PencilDoubleTapGestureValue**：描述 Apple Pencil 双击手势的值。
- **PencilSqueezeGestureValue**：描述 Apple Pencil 挤压手势的值。
- **PencilSqueezeGesturePhase**：描述 Apple Pencil 挤压手势的相位和值。
- **PencilHoverPose**：描述 Apple Pencil 在视图边界上方区域悬停的位置和距离的值。


---
source: https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/preferredPencilSqueezeAction
crawled: 2025-12-02T17:41:06Z
---

# preferredPencilSqueezeAction

**Instance Property**

The action that the user prefers to perform when squeezing their Apple Pencil, as selected in the Settings app.

## Declaration

```swift
var preferredPencilSqueezeAction: PencilPreferredAction { get }
```

## Discussion

You can read this value by creating a property with the [Environment](../Environment.zh-Hans.md) property wrapper and using it inside the action closure of the [onPencilSqueeze(perform:)](../View/onPencilSqueeze_perform.zh-Hans.md) view modifier as an indication of what to do when the user squeezes their Apple Pencil:

```swift
@Environment(\.preferredPencilSqueezeAction) private var preferredAction

var body: some View {
    MyDrawingCanvas()
        .onPencilSqueeze { phase in
            switch (phase, preferredAction) {
                ...
            }
        }
}
```

In macOS, this value cannot be changed by users and is always set to [showContextualPalette](../PencilPreferredAction/showContextualPalette.zh-Hans.md).

## Recognizing Apple Pencil gestures

- **onPencilDoubleTap(perform:)**: Adds an action to perform after the user double-taps their Apple Pencil.
- **onPencilSqueeze(perform:)**: Adds an action to perform when the user squeezes their Apple Pencil.
- **preferredPencilDoubleTapAction**: The action that the user prefers to perform after double-tapping their Apple Pencil, as selected in the Settings app.
- **PencilPreferredAction**: An action that the user prefers to perform after double-tapping their Apple Pencil.
- **PencilDoubleTapGestureValue**: Describes the value of an Apple Pencil double-tap gesture.
- **PencilSqueezeGestureValue**: Describes the value of an Apple Pencil squeeze gesture.
- **PencilSqueezeGesturePhase**: Describes the phase and value of an Apple Pencil squeeze gesture.
- **PencilHoverPose**: A value describing the location and distance of an Apple Pencil hovering in the area above a view’s bounds.

