--- 来源：https://developer.apple.com/documentation/SwiftUI/View/accessibilityActivationPoint(_:isEnabled:)

抓取时间：2025-11-30T21:28:59Z

---

# accessibilityActivationPoint(_:isEnabled:)

**实例方法**

元素的激活点是辅助技术用于启动手势的位置。

## 声明

```swift
nonisolated func accessibilityActivationPoint(_ activationPoint: CGPoint, isEnabled: Bool) -> ModifiedContent<Self, AccessibilityAttachmentModifier>
```

## 参数

- **activationPoint**：要应用的辅助功能激活点。

- **isEnabled**：如果为 true，则应用辅助功能激活点；否则，辅助功能激活点保持不变。

## 说明

使用此修饰符可确保即使向 VoiceOver 呈现元素的较大版本，较小元素的激活点仍然准确。

如果未提供激活点，则会从辅助功能元素的子元素或辅助功能框架的中心点获取激活点。

## 使手势更易于访问

- **accessibilityActivationPoint(_:)**：元素的激活点是辅助技术用于启动手势的位置。

- **accessibilityDragPoint(_:description:)**：辅助技术用于开始拖拽交互的位置。

- **accessibilityDragPoint(_:description:isEnabled:)**：辅助技术用于开始拖拽交互的位置。

- **accessibilityDropPoint(_:description:)**：辅助技术用于结束拖拽交互的位置。

- **accessibilityDropPoint(_:description:isEnabled:)**：辅助技术用于结束拖拽交互的位置。

- **accessibilityDirectTouch(_:options:)**：明确设置此辅助功能元素是否为直接触摸区域。直接触摸区域会将触摸事件直接传递给应用程序，而不是通过 VoiceOver 等辅助技术处理。该修饰符接受一个可选的 `AccessibilityDirectTouchOptions` 选项集，用于自定义直接触摸区域的功能。

- **accessibilityZoomAction(_:)**：为视图添加辅助功能缩放操作。操作允许 VoiceOver 等辅助技术通过调用该操作与视图进行交互。

- **AccessibilityDirectTouchOptions**：定义视图直接触摸区域功能的选项集。

- **AccessibilityZoomGestureAction**：用户使用 VoiceOver 等辅助技术执行的缩放手势的位置和方向信息。


---
source: https://developer.apple.com/documentation/SwiftUI/View/accessibilityActivationPoint(_:isEnabled:)
crawled: 2025-11-30T21:28:59Z
---

# accessibilityActivationPoint(_:isEnabled:)

**Instance Method**

The activation point for an element is the location assistive technologies use to initiate gestures.

## Declaration

```swift
nonisolated func accessibilityActivationPoint(_ activationPoint: CGPoint, isEnabled: Bool) -> ModifiedContent<Self, AccessibilityAttachmentModifier>
```

## Parameters

- **activationPoint**: The accessibility activation point to apply.
- **isEnabled**: If true the accessibility activation point is applied; otherwise the accessibility activation point is unchanged.

## Discussion

Use this modifier to ensure that the activation point for a small element remains accurate even if you present a larger version of the element to VoiceOver.

If an activation point is not provided, an activation point will be derived from one of the accessibility elements decedents or from the center of the accessibility frame.

## Making gestures accessible

- **accessibilityActivationPoint(_:)**: The activation point for an element is the location assistive technologies use to initiate gestures.
- **accessibilityDragPoint(_:description:)**: The point an assistive technology should use to begin a drag interaction.
- **accessibilityDragPoint(_:description:isEnabled:)**: The point an assistive technology should use to begin a drag interaction.
- **accessibilityDropPoint(_:description:)**: The point an assistive technology should use to end a drag interaction.
- **accessibilityDropPoint(_:description:isEnabled:)**: The point an assistive technology should use to end a drag interaction.
- **accessibilityDirectTouch(_:options:)**: Explicitly set whether this accessibility element is a direct touch area. Direct touch areas passthrough touch events to the app rather than being handled through an assistive technology, such as VoiceOver. The modifier accepts an optional `AccessibilityDirectTouchOptions` option set to customize the functionality of the direct touch area.
- **accessibilityZoomAction(_:)**: Adds an accessibility zoom action to the view. Actions allow assistive technologies, such as VoiceOver, to interact with the view by invoking the action.
- **AccessibilityDirectTouchOptions**: An option set that defines the functionality of a view’s direct touch area.
- **AccessibilityZoomGestureAction**: Position and direction information of a zoom gesture that someone performs with an assistive technology like VoiceOver.

