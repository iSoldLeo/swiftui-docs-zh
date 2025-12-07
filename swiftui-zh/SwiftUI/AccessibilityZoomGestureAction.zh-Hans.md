---
来源： https://developer.apple.com/documentation/SwiftUI/AccessibilityZoomGestureAction
抓取时间： 2025-12-02T17:44:05Z
---

# 无障碍缩放手势动作

**Structure**

某人使用 VoiceOver 等辅助技术执行缩放手势时的位置和方向信息。

## 声明

```swift
struct AccessibilityZoomGestureAction
```

## 获取动作方向

- **direction**：缩放手势的方向。
- **AccessibilityZoomGestureAction.Direction**：缩放手势的方向：与辅助技术执行的缩放手势运动相匹配的方向，例如 Voiceover 的缩放旋转器中的上下轻扫。

## 获取位置信息

- **location**：缩放手势的激活点，归一化为无障碍元素的框架。
- **point**：缩放手势在窗口坐标空间内的激活点。

### 实现手势无障碍

- **accessibilityActivationPoint(_:)**：元素的激活点是辅助技术用来启动手势的位置。
- **accessibilityActivationPoint(_:isEnabled:)**：元素的激活点是辅助技术用来启动手势的位置。
- **accessibilityDragPoint(_:description:)**：辅助技术应使用的开始拖动交互的点。
- **accessibilityDragPoint(_:description:isEnabled:)**：辅助技术应使用的开始拖动交互的点。
- **accessibilityDropPoint(_:description:)**：辅助技术用于结束拖动交互的点。
- **accessibilityDropPoint(_:description:isEnabled:)**：辅助技术应使用的结束拖动交互的点。
- **accessibilityDirectTouch(_:options:)**：明确设置此辅助元素是否为直接触摸区域。直接触摸区域将触摸事件传递给应用程序，而不是通过 VoiceOver 等辅助技术来处理。修改器接受一个可选的`AccessibilityDirectTouchOptions`选项设置，以自定义直接触摸区域的功能。
- **accessibilityZoomAction(_:)**：为视图添加无障碍缩放操作。操作允许 VoiceOver 等辅助技术通过调用操作与视图进行交互。
- **AccessibilityDirectTouchOptions**：定义视图直接触摸区域功能的选项集。


---
source: https://developer.apple.com/documentation/SwiftUI/AccessibilityZoomGestureAction
crawled: 2025-12-02T17:44:05Z
---

# AccessibilityZoomGestureAction

**Structure**

Position and direction information of a zoom gesture that someone performs with an assistive technology like VoiceOver.

## Declaration

```swift
struct AccessibilityZoomGestureAction
```

## Getting the action’s direction

- **direction**: The zoom gesture’s direction.
- **AccessibilityZoomGestureAction.Direction**: A direction that matches the movement of a zoom gesture performed by an assistive technology, such as a swipe up and down in Voiceover’s zoom rotor.

## Getting location information

- **location**: The zoom gesture’s activation point, normalized to the accessibility element’s frame.
- **point**: The zoom gesture’s activation point within the window’s coordinate space.

## Making gestures accessible

- **accessibilityActivationPoint(_:)**: The activation point for an element is the location assistive technologies use to initiate gestures.
- **accessibilityActivationPoint(_:isEnabled:)**: The activation point for an element is the location assistive technologies use to initiate gestures.
- **accessibilityDragPoint(_:description:)**: The point an assistive technology should use to begin a drag interaction.
- **accessibilityDragPoint(_:description:isEnabled:)**: The point an assistive technology should use to begin a drag interaction.
- **accessibilityDropPoint(_:description:)**: The point an assistive technology should use to end a drag interaction.
- **accessibilityDropPoint(_:description:isEnabled:)**: The point an assistive technology should use to end a drag interaction.
- **accessibilityDirectTouch(_:options:)**: Explicitly set whether this accessibility element is a direct touch area. Direct touch areas passthrough touch events to the app rather than being handled through an assistive technology, such as VoiceOver. The modifier accepts an optional `AccessibilityDirectTouchOptions` option set to customize the functionality of the direct touch area.
- **accessibilityZoomAction(_:)**: Adds an accessibility zoom action to the view. Actions allow assistive technologies, such as VoiceOver, to interact with the view by invoking the action.
- **AccessibilityDirectTouchOptions**: An option set that defines the functionality of a view’s direct touch area.

