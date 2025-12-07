--- 来源：https://developer.apple.com/documentation/SwiftUI/View/onPencilSqueeze(perform:)

抓取时间：2025-12-02T17:41:05Z

---

# onPencilSqueeze(perform:)

**实例方法**

添加用户挤压 Apple Pencil 时要执行的操作。

## 声明

```swift
nonisolated func onPencilSqueeze(perform action: @escaping (PencilSqueezeGesturePhase) -> Void) -> some View

```

## 参数

- **action**：用户挤压 Apple Pencil 时要执行的操作。

## 返回值

一个视图，当用户挤压 Apple Pencil 时执行 `action` 操作。

## 讨论

如果用户对挤压手势的设置在您的应用中有意义，您应该通过读取 [preferredPencilSqueezeAction](../EnvironmentValues/preferredPencilSqueezeAction.zh-Hans.md) 环境变量值来尊重用户的设置。如果不行，请考虑让用户在应用中指定自定义行为。

在下面的示例中，完成 Apple Pencil 的挤压手势将执行以下操作：

- 如果用户在“设置”应用中选择了“不执行任何操作”，则不执行任何操作；

- 如果用户在应用中配置了“套索”操作，则将工具切换到“套索”；

- 如果用户在应用中配置了“泼墨”操作，则泼墨；

- 如果用户未在应用中配置自定义操作，且在“设置”应用中选择了自定义上下文调色板，则显示自定义上下文调色板。

```swift
enum MyPencilAction: String {
    case spillInk
    ...
}

@Environment(\.preferredPencilSqueezeAction) private var preferredAction
@AppStorage("customPencilSqueezeAction") private var customAction: MyPencilAction?

@State private var contextualPaletteAnchor: PopoverAttachmentAnchor?
@State private var contextualPalettePresented = false

var body: some View {
    MyDrawingCanvas()
        .onPencilSqueeze { phase in
            guard preferredAction != .ignore else {
                // Skip if this is what the user prefers.
                return
            }
            if let customAction {
                // If a custom action is configured, respect it.
                if customAction == .spillInk {
                    switch phase {
                        // Spill the ink while the user is squeezing their Apple Pencil.
                    }
                }
            } else if preferredAction == .showContextualPalette, case let .ended(value) = phase {
                // Present a custom contextual palette if the user prefers it.
                contextualPaletteAnchor = value.hoverPose?.anchor.map { .point($0) }
                contextualPalettePresented = true
            }
        }
        .popover(
            isPresented: $contextualPalettePresented,
            attachmentAnchor: contextualPaletteAnchor ?? .point(.center)
        ) {
            MyContextualPalette()
        }
```

## 识别 Apple Pencil 手势

- **onPencilDoubleTap(perform:)**：添加用户双击 Apple Pencil 后要执行的操作。

- **preferredPencilDoubleTapAction**：用户在“设置”应用中选择的双击 Apple Pencil 后要执行的操作。

- **preferredPencilSqueezeAction**：用户在“设置”应用中选择的，挤压 Apple Pencil 时想要执行的操作。

- **PencilPreferredAction**：用户在双击 Apple Pencil 后想要执行的操作。

- **PencilDoubleTapGestureValue**：描述 Apple Pencil 双击手势的值。

- **PencilSqueezeGestureValue**：描述 Apple Pencil 挤压手势的值。

- **PencilSqueezeGesturePhase**：描述 Apple Pencil 挤压手势的阶段和值。

- **PencilHoverPose**：描述 Apple Pencil 悬停在视图边界上方区域的位置和距离的值。


---
source: https://developer.apple.com/documentation/SwiftUI/View/onPencilSqueeze(perform:)
crawled: 2025-12-02T17:41:05Z
---

# onPencilSqueeze(perform:)

**Instance Method**

Adds an action to perform when the user squeezes their Apple Pencil.

## Declaration

```swift
nonisolated func onPencilSqueeze(perform action: @escaping (PencilSqueezeGesturePhase) -> Void) -> some View

```

## Parameters

- **action**: The action to perform when the user squeezes their Apple Pencil.

## Return Value

A view that performs `action` when the user squeezes their Apple Pencil.

## Discussion

You should respect people’s setting for the squeeze gesture by reading the [preferredPencilSqueezeAction](../EnvironmentValues/preferredPencilSqueezeAction.zh-Hans.md) environment value, if the setting makes sense in your app. If it doesn’t, consider giving people a way to specify custom behavior in your app instead.

In the example below, completing an Apple Pencil squeeze gesture will…

- do nothing if this is what the user selected in the Settings app,
- switch the tool to ”Lasso” if this is the action they have configured in the app,
- spill the ink if this is the action they have configured in the app,
- present a custom contextual palette if they haven’t configured a custom action in the app and this is what they selected in the Settings app.

```swift
enum MyPencilAction: String {
    case spillInk
    ...
}

@Environment(\.preferredPencilSqueezeAction) private var preferredAction
@AppStorage("customPencilSqueezeAction") private var customAction: MyPencilAction?

@State private var contextualPaletteAnchor: PopoverAttachmentAnchor?
@State private var contextualPalettePresented = false

var body: some View {
    MyDrawingCanvas()
        .onPencilSqueeze { phase in
            guard preferredAction != .ignore else {
                // Skip if this is what the user prefers.
                return
            }
            if let customAction {
                // If a custom action is configured, respect it.
                if customAction == .spillInk {
                    switch phase {
                        // Spill the ink while the user is squeezing their Apple Pencil.
                    }
                }
            } else if preferredAction == .showContextualPalette, case let .ended(value) = phase {
                // Present a custom contextual palette if the user prefers it.
                contextualPaletteAnchor = value.hoverPose?.anchor.map { .point($0) }
                contextualPalettePresented = true
            }
        }
        .popover(
            isPresented: $contextualPalettePresented,
            attachmentAnchor: contextualPaletteAnchor ?? .point(.center)
        ) {
            MyContextualPalette()
        }
```



## Recognizing Apple Pencil gestures

- **onPencilDoubleTap(perform:)**: Adds an action to perform after the user double-taps their Apple Pencil.
- **preferredPencilDoubleTapAction**: The action that the user prefers to perform after double-tapping their Apple Pencil, as selected in the Settings app.
- **preferredPencilSqueezeAction**: The action that the user prefers to perform when squeezing their Apple Pencil, as selected in the Settings app.
- **PencilPreferredAction**: An action that the user prefers to perform after double-tapping their Apple Pencil.
- **PencilDoubleTapGestureValue**: Describes the value of an Apple Pencil double-tap gesture.
- **PencilSqueezeGestureValue**: Describes the value of an Apple Pencil squeeze gesture.
- **PencilSqueezeGesturePhase**: Describes the phase and value of an Apple Pencil squeeze gesture.
- **PencilHoverPose**: A value describing the location and distance of an Apple Pencil hovering in the area above a view’s bounds.

