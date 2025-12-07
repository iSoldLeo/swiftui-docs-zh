---
来源： https://developer.apple.com/documentation/SwiftUI/AccessibilityDirectTouchOptions
抓取时间： 2025-12-02T17:44:05Z
---

# 辅助功能直接触摸选项

**Structure**

定义视图直接触摸区域功能的选项集。

## 声明

```swift
struct AccessibilityDirectTouchOptions
```

## 获取选项

- **requiresActivation**：在 VoiceOver 等辅助技术通过用户操作（例如双击）激活直接触摸区域之前，阻止直接触摸区域的触摸直通。
- **silentOnTouch**：允许直接触摸区域在没有 VoiceOver 等辅助技术说话的情况下立即接收触摸事件。适用于在触摸时提供直接音频反馈的应用程序，这种反馈会与语音反馈发生冲突。

## 创建一组选项

- **init(rawValue:)**：创建一组直接触摸选项

## **init(rawValue:)**: 创建一组直接触摸选项

- **accessibilityActivationPoint(_:)**：元素的激活点是辅助技术用来启动手势的位置。
- **accessibilityActivationPoint(_:isEnabled:)**：元素的激活点是辅助技术用来启动手势的位置。
- **accessibilityDragPoint(_:description:)**：辅助技术应使用的开始拖动交互的点。
- **accessibilityDragPoint(_:description:isEnabled:)**：辅助技术应使用的开始拖动交互的点。
- **accessibilityDropPoint(_:description:)**：辅助技术用于结束拖动交互的点。
- **accessibilityDropPoint(_:description:isEnabled:)**：辅助技术应使用的结束拖动交互的点。
- **accessibilityDirectTouch(_:options:)**：明确设置此辅助元素是否为直接触摸区域。直接触摸区域将触摸事件传递给应用程序，而不是通过 VoiceOver 等辅助技术来处理。修改器接受一个可选的`AccessibilityDirectTouchOptions`选项设置，以自定义直接触摸区域的功能。
- **accessibilityZoomAction(_:)**：为视图添加无障碍缩放操作。操作允许 VoiceOver 等辅助技术通过调用操作与视图进行交互。
- **AccessibilityZoomGestureAction**：某人使用 VoiceOver 等辅助技术执行缩放手势时的位置和方向信息。

## 符合

- 等价
- 可通过数组字形表达
- 选项集
- 原始可表示
- 可发送
- 可发送元类
- 代数集


---
source: https://developer.apple.com/documentation/SwiftUI/AccessibilityDirectTouchOptions
crawled: 2025-12-02T17:44:05Z
---

# AccessibilityDirectTouchOptions

**Structure**

An option set that defines the functionality of a view’s direct touch area.

## Declaration

```swift
struct AccessibilityDirectTouchOptions
```

## Getting the options

- **requiresActivation**: Prevents touch passthrough with the direct touch area until an assistive technology, such as VoiceOver, has activated the direct touch area through a user action, for example a double tap.
- **silentOnTouch**: Allows a direct touch area to immediately receive touch events without an assitive technology, such as VoiceOver, speaking. Appropriate for apps that provide direct audio feedback on touch that would conflict with speech feedback.

## Creating a set of options

- **init(rawValue:)**: Create a set of direct touch options

## Making gestures accessible

- **accessibilityActivationPoint(_:)**: The activation point for an element is the location assistive technologies use to initiate gestures.
- **accessibilityActivationPoint(_:isEnabled:)**: The activation point for an element is the location assistive technologies use to initiate gestures.
- **accessibilityDragPoint(_:description:)**: The point an assistive technology should use to begin a drag interaction.
- **accessibilityDragPoint(_:description:isEnabled:)**: The point an assistive technology should use to begin a drag interaction.
- **accessibilityDropPoint(_:description:)**: The point an assistive technology should use to end a drag interaction.
- **accessibilityDropPoint(_:description:isEnabled:)**: The point an assistive technology should use to end a drag interaction.
- **accessibilityDirectTouch(_:options:)**: Explicitly set whether this accessibility element is a direct touch area. Direct touch areas passthrough touch events to the app rather than being handled through an assistive technology, such as VoiceOver. The modifier accepts an optional `AccessibilityDirectTouchOptions` option set to customize the functionality of the direct touch area.
- **accessibilityZoomAction(_:)**: Adds an accessibility zoom action to the view. Actions allow assistive technologies, such as VoiceOver, to interact with the view by invoking the action.
- **AccessibilityZoomGestureAction**: Position and direction information of a zoom gesture that someone performs with an assistive technology like VoiceOver.

## Conforms To

- Equatable
- ExpressibleByArrayLiteral
- OptionSet
- RawRepresentable
- Sendable
- SendableMetatype
- SetAlgebra

