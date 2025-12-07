--- 来源：https://developer.apple.com/documentation/SwiftUI/View/onPencilDoubleTap(perform:)

抓取时间：2025-12-02T17:41:04Z

---

# onPencilDoubleTap(perform:)

**实例方法**

添加用户双击 Apple Pencil 后要执行的操作。

## 声明

```swift
nonisolated func onPencilDoubleTap(perform action: @escaping (PencilDoubleTapGestureValue) -> Void) -> some View

```

## 参数

- **action**：用户双击 Apple Pencil 后要执行的操作。

## 返回值

一个在用户双击 Apple Pencil 后执行 `action` 操作的视图。

## 讨论

如果双击手势的设置在您的应用中合理，您应该通过读取 [preferredPencilDoubleTapAction](../EnvironmentValues/preferredPencilDoubleTapAction.zh-Hans.md) 环境变量值来尊重用户的设置。如果设置不合理，请考虑允许用户在您的应用中指定自定义行为。

在下面的示例中，双击 Apple Pencil 将执行以下操作：

- 如果用户在“设置”应用中选择了“无操作”，则不执行任何操作；

- 如果用户在应用中配置了“套索”操作，则将工具切换到“套索”；

- 如果用户未在应用中配置自定义操作，且在“设置”应用中选择了“橡皮擦”，则将工具切换到“橡皮擦”；

- 否则，将工具切换到上次使用的工具。

```swift
enum MyDrawingTool: Equatable {
    case brush
    case lasso
    case eraser
    ...
}

enum MyPencilAction: String {
    case switchLasso
    ...
}

@State private var currentTool = MyDrawingTool.brush
@State private var lastTool: MyDrawingTool?

@Environment(\.preferredPencilDoubleTapAction) private var globalAction
@AppStorage("customPencilDoubleTapAction") private var customAction: MyPencilAction?

var body: some View {
    MyDrawingCanvas()
        .onPencilDoubleTap { _ in
            guard globalAction != .ignore else {
                // Respect the user’s preference to ignore the double-tap gesture.
                return
            }
            if let customAction {
                // If a custom action is configured, respect it.
                if customAction == .switchLasso, currentTool != .lasso {
                     (currentTool, lastTool) = (.lasso, currentTool)
                }
            } else if globalAction == .switchEraser, currentTool != .eraser {
                // Switch to eraser if the user prefers it otherwise.
                (currentTool, lastTool) = (.eraser, currentTool)
            } else if let lastTool {
                // Switch to the last used tool by default.
                (currentTool, lastTool) = (lastTool, currentTool)
            }
        }
}
```

有关 Apple Pencil 双击手势的更多信息，请参阅 [https://developer.apple.com/design/human-interface-guidelines/apple-pencil-and-scribble#Double-tap]。

## 识别 Apple Pencil 手势

- **onPencilSqueeze(perform:)**：添加用户挤压 Apple Pencil 时要执行的操作。

- **preferredPencilDoubleTapAction**：用户在“设置”应用中选择的，在双击 Apple Pencil 后要执行的操作。

- **preferredPencilSqueezeAction**：用户在“设置”应用中选择的，在挤压 Apple Pencil 时要执行的操作。

- **PencilPreferredAction**：用户在双击 Apple Pencil 后要执行的操作。

- **PencilDoubleTapGestureValue**：描述 Apple Pencil 双击手势的值。

- **PencilSqueezeGestureValue**：描述 Apple Pencil 挤压手势的值。

- **PencilSqueezeGesturePhase**：描述 Apple Pencil 挤压手势的阶段和值。

- **PencilHoverPose**：描述 Apple Pencil 悬停在视图边界上方区域的位置和距离的值。


---
source: https://developer.apple.com/documentation/SwiftUI/View/onPencilDoubleTap(perform:)
crawled: 2025-12-02T17:41:04Z
---

# onPencilDoubleTap(perform:)

**Instance Method**

Adds an action to perform after the user double-taps their Apple Pencil.

## Declaration

```swift
nonisolated func onPencilDoubleTap(perform action: @escaping (PencilDoubleTapGestureValue) -> Void) -> some View

```

## Parameters

- **action**: The action to perform after the user double-taps their Apple Pencil.

## Return Value

A view that performs `action` after the user double-taps their Apple Pencil.

## Discussion

You should respect people’s setting for the double-tap gesture by reading the [preferredPencilDoubleTapAction](../EnvironmentValues/preferredPencilDoubleTapAction.zh-Hans.md) environment value, if the setting makes sense in your app. If it doesn’t, consider giving people a way to specify custom behavior in your app instead.

In the example below, double-tapping an Apple Pencil will…

- do nothing if this is what the user selected in the Settings app,
- switch the tool to ”Lasso” if this is the action they have configured in the app,
- switch the tool to ”Eraser” if they haven’t configured a custom action in the app and this is what they selected in the Settings app,
- switch the tool to the last used one otherwise.

```swift
enum MyDrawingTool: Equatable {
    case brush
    case lasso
    case eraser
    ...
}

enum MyPencilAction: String {
    case switchLasso
    ...
}

@State private var currentTool = MyDrawingTool.brush
@State private var lastTool: MyDrawingTool?

@Environment(\.preferredPencilDoubleTapAction) private var globalAction
@AppStorage("customPencilDoubleTapAction") private var customAction: MyPencilAction?

var body: some View {
    MyDrawingCanvas()
        .onPencilDoubleTap { _ in
            guard globalAction != .ignore else {
                // Respect the user’s preference to ignore the double-tap gesture.
                return
            }
            if let customAction {
                // If a custom action is configured, respect it.
                if customAction == .switchLasso, currentTool != .lasso {
                     (currentTool, lastTool) = (.lasso, currentTool)
                }
            } else if globalAction == .switchEraser, currentTool != .eraser {
                // Switch to eraser if the user prefers it otherwise.
                (currentTool, lastTool) = (.eraser, currentTool)
            } else if let lastTool {
                // Switch to the last used tool by default.
                (currentTool, lastTool) = (lastTool, currentTool)
            }
        }
}
```

For more information about Apple Pencil double-tap gestures, see [https://developer.apple.com/design/human-interface-guidelines/apple-pencil-and-scribble#Double-tap].



## Recognizing Apple Pencil gestures

- **onPencilSqueeze(perform:)**: Adds an action to perform when the user squeezes their Apple Pencil.
- **preferredPencilDoubleTapAction**: The action that the user prefers to perform after double-tapping their Apple Pencil, as selected in the Settings app.
- **preferredPencilSqueezeAction**: The action that the user prefers to perform when squeezing their Apple Pencil, as selected in the Settings app.
- **PencilPreferredAction**: An action that the user prefers to perform after double-tapping their Apple Pencil.
- **PencilDoubleTapGestureValue**: Describes the value of an Apple Pencil double-tap gesture.
- **PencilSqueezeGestureValue**: Describes the value of an Apple Pencil squeeze gesture.
- **PencilSqueezeGesturePhase**: Describes the phase and value of an Apple Pencil squeeze gesture.
- **PencilHoverPose**: A value describing the location and distance of an Apple Pencil hovering in the area above a view’s bounds.

