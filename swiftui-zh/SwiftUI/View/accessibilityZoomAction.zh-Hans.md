--- 来源：https://developer.apple.com/documentation/SwiftUI/View/accessibilityZoomAction(_:)

抓取时间：2025-12-02T17:44:04Z

---

# accessibilityZoomAction(_:)

**实例方法**

向视图添加辅助功能缩放操作。操作允许 VoiceOver 等辅助技术通过调用该操作与视图进行交互。

## 声明

```swift
nonisolated func accessibilityZoomAction(_ handler: @escaping (AccessibilityZoomGestureAction) -> Void) -> ModifiedContent<Self, AccessibilityAttachmentModifier>
```

## 说明

例如，以下示例展示了如何使用缩放操作来改变具有 `MagnificationGesture` 属性的形状的缩放比例。

```swift
var body: some View {
    Circle()
        .scaleEffect(magnifyBy)
        .gesture(magnification)
        .accessibilityLabel("Circle Magnifier")
        .accessibilityZoomAction { action in
            switch action.direction {
            case .zoomIn:
                magnifyBy += 0.5
            case .zoomOut:
                 magnifyBy -= 0.5
            }
        }
}
```

## 使手势可访问

- **accessibilityActivationPoint(_:)**：元素的激活点是辅助技术用于启动手势的位置。

- **accessibilityActivationPoint(_:isEnabled:)**：元素的激活点是辅助技术用于启动手势的位置。

- **accessibilityDragPoint(_:description:)**：辅助技术用于开始拖拽交互的位置。

- **accessibilityDragPoint(_:description:isEnabled:)**：辅助技术用于开始拖拽交互的位置。

- **accessibilityDropPoint(_:description:)**：辅助技术用于结束拖拽交互的位置。

- **accessibilityDropPoint(_:description:isEnabled:)**：辅助技术用于结束拖拽交互的位置。

- **accessibilityDirectTouch(_:options:)**：显式设置此辅助功能元素是否为直接触摸区域。直接触摸区域会将触摸事件传递给应用程序，而不是通过 VoiceOver 等辅助技术处理。此修饰符接受一个可选的 `AccessibilityDirectTouchOptions` 选项集，用于自定义直接触摸区域的功能。

- **AccessibilityDirectTouchOptions**：定义视图直接触摸区域功能的选项集。

- **AccessibilityZoomGestureAction**：用户使用 VoiceOver 等辅助技术执行缩放手势的位置和方向信息。


---
source: https://developer.apple.com/documentation/SwiftUI/View/accessibilityZoomAction(_:)
crawled: 2025-12-02T17:44:04Z
---

# accessibilityZoomAction(_:)

**Instance Method**

Adds an accessibility zoom action to the view. Actions allow assistive technologies, such as VoiceOver, to interact with the view by invoking the action.

## Declaration

```swift
nonisolated func accessibilityZoomAction(_ handler: @escaping (AccessibilityZoomGestureAction) -> Void) -> ModifiedContent<Self, AccessibilityAttachmentModifier>
```

## Discussion

For example, this is how a zoom action is used to transform the scale of a shape which has a `MagnificationGesture`.

```swift
var body: some View {
    Circle()
        .scaleEffect(magnifyBy)
        .gesture(magnification)
        .accessibilityLabel("Circle Magnifier")
        .accessibilityZoomAction { action in
            switch action.direction {
            case .zoomIn:
                magnifyBy += 0.5
            case .zoomOut:
                 magnifyBy -= 0.5
            }
        }
}
```

## Making gestures accessible

- **accessibilityActivationPoint(_:)**: The activation point for an element is the location assistive technologies use to initiate gestures.
- **accessibilityActivationPoint(_:isEnabled:)**: The activation point for an element is the location assistive technologies use to initiate gestures.
- **accessibilityDragPoint(_:description:)**: The point an assistive technology should use to begin a drag interaction.
- **accessibilityDragPoint(_:description:isEnabled:)**: The point an assistive technology should use to begin a drag interaction.
- **accessibilityDropPoint(_:description:)**: The point an assistive technology should use to end a drag interaction.
- **accessibilityDropPoint(_:description:isEnabled:)**: The point an assistive technology should use to end a drag interaction.
- **accessibilityDirectTouch(_:options:)**: Explicitly set whether this accessibility element is a direct touch area. Direct touch areas passthrough touch events to the app rather than being handled through an assistive technology, such as VoiceOver. The modifier accepts an optional `AccessibilityDirectTouchOptions` option set to customize the functionality of the direct touch area.
- **AccessibilityDirectTouchOptions**: An option set that defines the functionality of a view’s direct touch area.
- **AccessibilityZoomGestureAction**: Position and direction information of a zoom gesture that someone performs with an assistive technology like VoiceOver.

