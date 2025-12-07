--- 来源：https://developer.apple.com/documentation/SwiftUI/View/accessibilityDirectTouch(_:options:)

抓取时间：2025-12-02T17:44:03Z

---

# accessibilityDirectTouch(_:options:)

**实例方法**

显式设置此辅助功能元素是否为直接触摸区域。直接触摸区域会将触摸事件传递给应用程序，而不是通过 VoiceOver 等辅助技术处理。此修饰符接受一个可选的 `AccessibilityDirectTouchOptions` 选项集，用于自定义直接触摸区域的功能。

## 声明

```swift
nonisolated func accessibilityDirectTouch(_ isDirectTouchArea: Bool = true, options: AccessibilityDirectTouchOptions = []) -> ModifiedContent<Self, AccessibilityAttachmentModifier>
```

## 讨论

例如，以下示例展示了如何使用直接触摸区域，使 VoiceOver 用户能够与由 `RotationGesture` 控制的 `rotationEffect` 视图进行交互。直接触摸区域需要用户先激活才能使用。

```swift
var body: some View {
    Rectangle()
        .frame(width: 200, height: 200, alignment: .center)
        .rotationEffect(angle)
        .gesture(rotation)
        .accessibilityDirectTouch(options: .requiresActivation)
}
```

## 使手势操作更易于访问

- **accessibilityActivationPoint(_:)**：元素的激活点是辅助技术用于启动手势的位置。

- **accessibilityActivationPoint(_:isEnabled:)**：元素的激活点是辅助技术用于启动手势的位置。

- **accessibilityDragPoint(_:description:)**：辅助技术用于开始拖拽交互的位置。

- **accessibilityDragPoint(_:description:isEnabled:)**：辅助技术用于开始拖拽交互的位置。

- **accessibilityDropPoint(_:description:)**：辅助技术用于结束拖拽交互的位置。

- **accessibilityDropPoint(_:description:isEnabled:)**：辅助技术用于结束拖拽交互的位置。

- **accessibilityZoomAction(_:)**：为视图添加辅助功能缩放操作。操作允许 VoiceOver 等辅助技术通过调用该操作与视图进行交互。

- **AccessibilityDirectTouchOptions**：定义视图直接触摸区域功能的选项集。

- **AccessibilityZoomGestureAction**：用户使用 VoiceOver 等辅助技术执行缩放手势的位置和方向信息。


---
source: https://developer.apple.com/documentation/SwiftUI/View/accessibilityDirectTouch(_:options:)
crawled: 2025-12-02T17:44:03Z
---

# accessibilityDirectTouch(_:options:)

**Instance Method**

Explicitly set whether this accessibility element is a direct touch area. Direct touch areas passthrough touch events to the app rather than being handled through an assistive technology, such as VoiceOver. The modifier accepts an optional `AccessibilityDirectTouchOptions` option set to customize the functionality of the direct touch area.

## Declaration

```swift
nonisolated func accessibilityDirectTouch(_ isDirectTouchArea: Bool = true, options: AccessibilityDirectTouchOptions = []) -> ModifiedContent<Self, AccessibilityAttachmentModifier>
```

## Discussion

For example, this is how a direct touch area would allow a VoiceOver user to interact with a view with a `rotationEffect` controlled by a `RotationGesture`. The direct touch area would require a user to activate the area before using the direct touch area.

```swift
var body: some View {
    Rectangle()
        .frame(width: 200, height: 200, alignment: .center)
        .rotationEffect(angle)
        .gesture(rotation)
        .accessibilityDirectTouch(options: .requiresActivation)
}
```

## Making gestures accessible

- **accessibilityActivationPoint(_:)**: The activation point for an element is the location assistive technologies use to initiate gestures.
- **accessibilityActivationPoint(_:isEnabled:)**: The activation point for an element is the location assistive technologies use to initiate gestures.
- **accessibilityDragPoint(_:description:)**: The point an assistive technology should use to begin a drag interaction.
- **accessibilityDragPoint(_:description:isEnabled:)**: The point an assistive technology should use to begin a drag interaction.
- **accessibilityDropPoint(_:description:)**: The point an assistive technology should use to end a drag interaction.
- **accessibilityDropPoint(_:description:isEnabled:)**: The point an assistive technology should use to end a drag interaction.
- **accessibilityZoomAction(_:)**: Adds an accessibility zoom action to the view. Actions allow assistive technologies, such as VoiceOver, to interact with the view by invoking the action.
- **AccessibilityDirectTouchOptions**: An option set that defines the functionality of a view’s direct touch area.
- **AccessibilityZoomGestureAction**: Position and direction information of a zoom gesture that someone performs with an assistive technology like VoiceOver.

