--- 来源：https://developer.apple.com/documentation/SwiftUI/Accessible-controls
抓取时间：2025-12-02T16:49:10Z

---

# 辅助功能控件

**API 集合**

改进应用操作的访问体验。

## 概述

帮助使用辅助技术的用户访问应用中的控件。

有关设计指南，请参阅《人机界面指南》辅助功能部分的 [doc://com.apple.documentation/design/Human-Interface-Guidelines/accessibility#Buttons-and-controls]。

## 向视图添加操作

- **accessibilityAction(_:_:)**：向视图添加辅助功能操作。操作允许 VoiceOver 等辅助技术通过调用该操作与视图进行交互。

- **accessibilityActions(_:)**：向视图添加多个辅助功能操作。

- **accessibilityAction(named:_:)**：向视图添加辅助功能操作。操作允许 VoiceOver 等辅助技术通过调用该操作与视图进行交互。

- **accessibilityAction(action:label:)**：向视图添加辅助功能操作。操作允许 VoiceOver 等辅助技术通过调用该操作与视图进行交互。

- **accessibilityAction(intent:label:)**：向视图添加一个由 `label` 的内容标记的辅助功能操作。操作允许 VoiceOver 等辅助技术通过调用该操作与视图进行交互。执行该操作时，将调用 `intent`。

- **accessibilityAction(_:intent:)**：向视图添加一个代表 `actionKind` 的辅助功能操作。操作允许辅助技术（例如 VoiceOver）通过调用操作与视图进行交互。执行操作时，将调用 `intent`。

- **accessibilityAction(named:intent:)**：向视图添加一个名为 `name` 的辅助功能操作。操作允许辅助技术（例如 VoiceOver）通过调用操作与视图进行交互。执行操作时，将调用 `intent`。

- **accessibilityAdjustableAction(_:)**：向视图添加一个辅助功能可调节操作。操作允许辅助技术（例如 VoiceOver）通过调用操作与视图进行交互。

- **accessibilityScrollAction(_:)**：向视图添加一个辅助功能滚动操作。操作允许辅助技术（例如 VoiceOver）通过调用操作与视图进行交互。

- **accessibilityActions(category:_:)**：为视图添加多个具有特定类别的辅助功能操作。操作允许 VoiceOver 等辅助技术通过调用操作与视图交互，并按类别分组。当对视图应用多个具有相同类别的操作修饰符时，这些操作将合并在一起。

- **AccessibilityActionKind**：定义可用辅助功能操作类型的结构。

- **AccessibilityAdjustmentDirection**：进行辅助功能调整时使用的方向指示器。

- **AccessibilityActionCategory**：指定由系统提供和命名的辅助功能操作类别。

## 为用户提供快捷操作

- **accessibilityQuickAction(style:content:)**：添加一个在激活时由系统显示的快捷操作。

- **accessibilityQuickAction(style:isActive:content:)**：添加一个在激活时由系统显示的快捷操作。

- **AccessibilityQuickActionStyle**：描述辅助功能快捷操作呈现方式的类型。

## 使手势更易于访问

- **accessibilityActivationPoint(_:)**：元素的激活点是辅助技术用于启动手势的位置。

- **accessibilityActivationPoint(_:isEnabled:)**：元素的激活点是辅助技术用于启动手势的位置。

- **accessibilityDragPoint(_:description:)**：辅助技术用于开始拖拽交互的位置。

- **accessibilityDragPoint(_:description:isEnabled:)**：辅助技术用于开始拖拽交互的位置。

- **accessibilityDropPoint(_:description:)**：辅助技术用于结束拖拽交互的位置。

- **accessibilityDropPoint(_:description:isEnabled:)**：辅助技术用于结束拖拽交互的位置。

- **accessibilityDirectTouch(_:options:)**：明确设置此辅助功能元素是否为直接触摸区域。直接触摸区域会将触摸事件传递给应用程序，而不是通过 VoiceOver 等辅助技术处理。此修饰符接受一个可选的 `AccessibilityDirectTouchOptions` 选项集，用于自定义直接触摸区域的功能。

- **accessibilityZoomAction(_:)**：向视图添加辅助功能缩放操作。操作允许 VoiceOver 等辅助技术通过调用该操作与视图进行交互。

- **AccessibilityDirectTouchOptions**：定义视图直接触摸区域功能的选项集。

- **AccessibilityZoomGestureAction**：用户使用 VoiceOver 等辅助技术执行的缩放手势的位置和方向信息。

## 控制焦点

- **accessibilityFocused(_:)**：通过将辅助功能元素的焦点状态绑定到给定的布尔值来修改此视图。

- **accessibilityFocused(_:equals:)**：通过将辅助功能元素的焦点状态绑定到给定的状态值来修改此视图。

- **AccessibilityFocusState**：一种属性包装类型，可以读取和写入 SwiftUI 在任何激活的辅助功能技术（例如 VoiceOver）的焦点更改时更新的值。

## 管理交互性

- **accessibilityRespondsToUserInteraction(_:)**：显式设置此辅助功能元素是否响应用户交互，从而是否可以通过切换控制、语音控制或完全键盘访问等技术进行交互。

- **accessibilityRespondsToUserInteraction(_:isEnabled:)**：显式设置此辅助功能元素是否响应用户交互，从而是否可以通过切换控制、语音控制或完全键盘访问等技术进行交互。

## 无障碍功能

- **无障碍功能基础**：确保您的 SwiftUI 应用对所有人（包括残障人士）都易于使用。

- **无障碍外观**：增强应用界面内容的易读性。

- **无障碍描述**：描述界面元素，帮助用户理解其含义。

- **无障碍导航**：使用户能够使用旋转器导航到特定的用户界面元素。


---
source: https://developer.apple.com/documentation/SwiftUI/Accessible-controls
crawled: 2025-12-02T16:49:10Z
---

# Accessible controls

**API Collection**

Improve access to actions that your app can undertake.

## Overview

Help people using assistive technologies to gain access to controls in your app.



For design guidance, see [doc://com.apple.documentation/design/Human-Interface-Guidelines/accessibility#Buttons-and-controls] in the Accessibility section of the Human Interface Guidelines.

## Adding actions to views

- **accessibilityAction(_:_:)**: Adds an accessibility action to the view. Actions allow assistive technologies, such as the VoiceOver, to interact with the view by invoking the action.
- **accessibilityActions(_:)**: Adds multiple accessibility actions to the view.
- **accessibilityAction(named:_:)**: Adds an accessibility action to the view. Actions allow assistive technologies, such as the VoiceOver, to interact with the view by invoking the action.
- **accessibilityAction(action:label:)**: Adds an accessibility action to the view. Actions allow assistive technologies, such as the VoiceOver, to interact with the view by invoking the action.
- **accessibilityAction(intent:label:)**: Adds an accessibility action labeled by the contents of `label` to the view. Actions allow assistive technologies, such as the VoiceOver, to interact with the view by invoking the action. When the action is performed, the `intent` will be invoked.
- **accessibilityAction(_:intent:)**: Adds an accessibility action representing `actionKind` to the view. Actions allow assistive technologies, such as the VoiceOver, to interact with the view by invoking the action. When the action is performed, the `intent` will be invoked.
- **accessibilityAction(named:intent:)**: Adds an accessibility action labeled `name` to the view. Actions allow assistive technologies, such as the VoiceOver, to interact with the view by invoking the action. When the action is performed, the `intent` will be invoked.
- **accessibilityAdjustableAction(_:)**: Adds an accessibility adjustable action to the view. Actions allow assistive technologies, such as the VoiceOver, to interact with the view by invoking the action.
- **accessibilityScrollAction(_:)**: Adds an accessibility scroll action to the view. Actions allow assistive technologies, such as the VoiceOver, to interact with the view by invoking the action.
- **accessibilityActions(category:_:)**: Adds multiple accessibility actions to the view with a specific category. Actions allow assistive technologies, such as VoiceOver, to interact with the view by invoking the action and are grouped by their category. When multiple action modifiers with an equal category are applied to the view, the actions are combined together.
- **AccessibilityActionKind**: The structure that defines the kinds of available accessibility actions.
- **AccessibilityAdjustmentDirection**: A directional indicator you use when making an accessibility adjustment.
- **AccessibilityActionCategory**: Designates an accessibility action category that is provided and named by the system.

## Offering Quick Actions to people

- **accessibilityQuickAction(style:content:)**: Adds a quick action to be shown by the system when active.
- **accessibilityQuickAction(style:isActive:content:)**: Adds a quick action to be shown by the system when active.
- **AccessibilityQuickActionStyle**: A type that describes the presentation style of an accessibility quick action.

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
- **AccessibilityZoomGestureAction**: Position and direction information of a zoom gesture that someone performs with an assistive technology like VoiceOver.

## Controlling focus

- **accessibilityFocused(_:)**: Modifies this view by binding its accessibility element’s focus state to the given boolean state value.
- **accessibilityFocused(_:equals:)**: Modifies this view by binding its accessibility element’s focus state to the given state value.
- **AccessibilityFocusState**: A property wrapper type that can read and write a value that SwiftUI updates as the focus of any active accessibility technology, such as VoiceOver, changes.

## Managing interactivity

- **accessibilityRespondsToUserInteraction(_:)**: Explicitly set whether this Accessibility element responds to user interaction and would thus be interacted with by technologies such as Switch Control, Voice Control or Full Keyboard Access.
- **accessibilityRespondsToUserInteraction(_:isEnabled:)**: Explicitly set whether this Accessibility element responds to user interaction and would thus be interacted with by technologies such as Switch Control, Voice Control or Full Keyboard Access.

## Accessibility

- **Accessibility fundamentals**: Make your SwiftUI apps accessible to everyone, including people with disabilities.
- **Accessible appearance**: Enhance the legibility of content in your app’s interface.
- **Accessible descriptions**: Describe interface elements to help people understand what they represent.
- **Accessible navigation**: Enable users to navigate to specific user interface elements using rotors.

