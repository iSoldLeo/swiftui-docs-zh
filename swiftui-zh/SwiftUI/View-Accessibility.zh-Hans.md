---

来源：https://developer.apple.com/documentation/SwiftUI/View-Accessibility
抓取时间：2025-12-02T17:22:09Z

---

# 辅助功能修饰符

**API 集合**

让您的 SwiftUI 应用对所有人（包括残障人士）都易于使用。

## 概述

与所有 Apple UI 框架一样，SwiftUI 内置了辅助功能支持。该框架会检查导航视图、列表、文本字段、滑块、按钮等常用元素，并默认提供基本的辅助功能标签和值。您无需进行任何额外操作即可启用这些标准辅助功能。

SwiftUI 还提供了一些工具来帮助您增强应用的辅助功能。例如，您可以使用 [accessibilityLabel(_:)](View/accessibilityLabel.zh-Hans.md) 或 [accessibilityValue(_:)](View/accessibilityValue.zh-Hans.md) 视图修饰符，显式地为 UI 元素添加辅助功能标签。

要了解更多关于如何为应用添加辅助功能的信息，请参阅 [Accessibility-fundamentals](Accessibility-fundamentals.zh-Hans.md)。

## 标签

- **accessibilityLabel(_:)**：为视图添加描述其内容的标签。

- **accessibilityLabel(_:isEnabled:)**：为视图添加描述其内容的标签。

- **accessibilityLabel(content:)**：为视图添加描述其内容的标签。

- **accessibilityInputLabels(_:)**：设置用户用于识别视图的备用输入标签。

- **accessibilityInputLabels(_:isEnabled:)**：设置用户用于识别视图的备用输入标签。

- **accessibilityLabeledPair(role:id:in:)**：将表示标签的辅助功能元素与对应内容的元素配对。

## 值

- **accessibilityValue(_:)**：为视图包含的值添加文本描述。

- **accessibilityValue(_:isEnabled:)**：为视图包含的值添加文本描述。

## 提示

- **accessibilityHint(_:)**：向用户说明执行视图操作后会发生什么。

- **accessibilityHint(_:isEnabled:)**：向用户说明执行视图操作后会发生什么。

## 操作

- **accessibilityAction(_:_:)**：向视图添加辅助功能操作。操作允许 VoiceOver 等辅助技术通过调用该操作与视图进行交互。

- **accessibilityActions(_:)**：向视图添加多个辅助功能操作。

- **accessibilityAction(named:_:)**：向视图添加辅助功能操作。操作允许 VoiceOver 等辅助技术通过调用该操作与视图进行交互。

- **accessibilityAction(action:label:)**：向视图添加辅助功能操作。操作允许 VoiceOver 等辅助技术通过调用该操作与视图进行交互。

- **accessibilityAction(intent:label:)**：向视图添加一个由 `label` 的内容标记的辅助功能操作。操作允许 VoiceOver 等辅助技术通过调用该操作与视图进行交互。执行该操作时，将调用 `intent`。

- **accessibilityAction(_:intent:)**：向视图添加一个代表 `actionKind` 的辅助功能操作。操作允许辅助技术（例如 VoiceOver）通过调用操作与视图进行交互。执行操作时，将调用 `intent`。

- **accessibilityAction(named:intent:)**：向视图添加一个名为 `name` 的辅助功能操作。操作允许辅助技术（例如 VoiceOver）通过调用操作与视图进行交互。执行操作时，将调用 `intent`。

- **accessibilityAdjustableAction(_:)**：向视图添加一个辅助功能可调节操作。操作允许辅助技术（例如 VoiceOver）通过调用操作与视图进行交互。

- **accessibilityScrollAction(_:)**：向视图添加一个辅助功能滚动操作。操作允许辅助技术（例如 VoiceOver）通过调用操作与视图进行交互。

## 手势

- **accessibilityActivationPoint(_:)**：元素的激活点是辅助技术用于启动手势的位置。

- **accessibilityActivationPoint(_:isEnabled:)**：元素的激活点是辅助技术用于启动手势的位置。

- **accessibilityDragPoint(_:description:)**：辅助技术用于开始拖拽交互的位置。

- **accessibilityDragPoint(_:description:isEnabled:)**：辅助技术用于开始拖拽交互的位置。

- **accessibilityDropPoint(_:description:)**：辅助技术用于结束拖拽交互的位置。

- **accessibilityDropPoint(_:description:isEnabled:)**：辅助技术用于结束拖拽交互的位置。

- **accessibilityDirectTouch(_:options:)**：明确设置此辅助功能元素是否为直接触摸区域。直接触摸区域会将触摸事件直接传递给应用程序，而不是通过 VoiceOver 等辅助技术处理。该修饰符接受一个可选的 `AccessibilityDirectTouchOptions` 选项集，用于自定义直接触摸区域的功能。

- **accessibilityZoomAction(_:)**：为视图添加辅助功能缩放操作。操作允许 VoiceOver 等辅助技术通过调用该操作与视图进行交互。

## 元素

- **accessibilityElement(children:)**：创建新的辅助功能元素，或修改现有辅助功能元素的 [AccessibilityChildBehavior](AccessibilityChildBehavior.zh-Hans.md)。

- **accessibilityChildren(children:)**：将现有辅助功能元素的子元素替换为一个或多个新的合成辅助功能元素。

- **accessibilityHidden(_:)**：指定是否对系统辅助功能隐藏此视图。

- **accessibilityHidden(_:isEnabled:)**：指定是否从系统辅助功能中隐藏此视图。

## 自定义控件

- **accessibilityRepresentation(representation:)**：将此视图的一个或多个辅助功能元素替换为新的辅助功能元素。

- **accessibilityRespondsToUserInteraction(_:)**：显式设置此辅助功能元素是否响应用户交互，从而是否可通过切换控制、语音控制或全键盘访问等技术进行交互。

- **accessibilityRespondsToUserInteraction(_:isEnabled:)**：显式设置此辅助功能元素是否响应用户交互，从而是否可通过切换控制、语音控制或全键盘访问等技术进行交互。

## 自定义内容

- **accessibilityCustomContent(_:_:importance:)**：向视图添加其他辅助功能信息。

## 使用转子

- **accessibilityRotor(_:entries:)**：创建一个具有指定用户可见标签的辅助功能转子，并从内容闭包生成条目。

- **accessibilityRotor(_:entries:entryID:entryLabel:)**：创建一个具有指定用户可见标签和条目的辅助功能转子。

- **accessibilityRotor(_:entries:entryLabel:)**：创建一个具有指定用户可见标签和条目的辅助功能转子。

- **accessibilityRotor(_:textRanges:)**：创建一个具有指定用户可见标签的辅助功能转子，并为每个指定范围创建条目。该转子将附加到当前的辅助功能元素，每个条目将位于该元素的指定范围内。

## 配置转子

- **accessibilityRotorEntry(id:in:)**：定义一个显式标识符，将此视图的辅助功能元素与辅助功能转子中的条目关联起来。

- **accessibilityLinkedGroup(id:in:)**：链接多个辅助功能元素，以便用户能够快速地从一个元素导航到另一个元素，即使这些元素在辅助功能层级结构中彼此并不相邻。

- **accessibilitySortPriority(_:)**：设置此视图辅助功能元素相对于同一层级其他元素的排序优先级。

## 焦点

- **accessibilityFocused(_:)**：通过将辅助功能元素的焦点状态绑定到给定的布尔值来修改此视图。

- **accessibilityFocused(_:equals:)**：通过将辅助功能元素的焦点状态绑定到给定的状态值来修改此视图。

## 特性

- **accessibilityAddTraits(_:)**：向视图添加给定的特性。

- **accessibilityRemoveTraits(_:)**：从此视图中移除给定的特性。

## 标识

- **accessibilityIdentifier(_:)**：使用您指定的字符串来标识视图。

- **accessibilityIdentifier(_:isEnabled:)**：使用您指定的字符串来标识视图。

## 颜色反转

- **accessibilityIgnoresInvertColors(_:)**：设置此视图是否应忽略系统智能反转设置。

## 内容描述

- **accessibilityTextContentType(_:)**：设置辅助功能文本内容类型。

- **accessibilityHeading(_:)**：设置此标题的辅助功能级别。

## 旁白

- **speechAdjustedPitch(_:)**：提高或降低朗读文本的音调。

- **speechAlwaysIncludesPunctuation(_:)**：设置旁白是否应始终朗读文本视图中的所有标点符号。

- **speechAnnouncementsQueued(_:)**：控制是否将待处理的公告排队到现有语音之后，而不是打断正在进行的语音。

- **speechSpellsOutCharacters(_:)**：设置 VoiceOver 是否逐字符朗读文本视图的内容。

## 图表

- **accessibilityChartDescriptor(_:)**：为表示图表的视图添加描述符，使所有用户都能访问图表的内容。

## 大内容

- **accessibilityShowsLargeContentViewer()**：添加一个默认的大内容视图，供大内容查看器显示。

- **accessibilityShowsLargeContentViewer(_:)**：添加一个自定义的大内容视图，供大内容查看器显示。

## 快捷操作

- **accessibilityQuickAction(style:content:)**：添加一个快捷操作，在激活时由系统显示。

- **accessibilityQuickAction(style:isActive:content:)**：添加一个快捷操作，激活后由系统显示。

## 配置视图元素

- **外观修饰符**：配置视图的前景色和背景色、控件以及可见性。

- **文本和符号修饰符**：管理视图中文本的渲染、选择和输入。

- **辅助视图修饰符**：添加和配置辅助视图，例如工具栏和上下文菜单。

- **图表视图修饰符**：配置使用 Swift Charts 声明的图表。


---
source: https://developer.apple.com/documentation/SwiftUI/View-Accessibility
crawled: 2025-12-02T17:22:09Z
---

# Accessibility modifiers

**API Collection**

Make your SwiftUI apps accessible to everyone, including people with disabilities.

## Overview

Like all Apple UI frameworks, SwiftUI comes with built-in accessibility support. The framework introspects common elements like navigation views, lists, text fields, sliders, buttons, and so on, and provides basic accessibility labels and values by default. You don’t have to do any extra work to enable these standard accessibility features.

SwiftUI also provides tools to help you enhance the accessibility of your app. For example, you can explicitly add accessibility labels to elements in your UI using the [accessibilityLabel(_:)](View/accessibilityLabel.zh-Hans.md) or the [accessibilityValue(_:)](View/accessibilityValue.zh-Hans.md) view modifier.

To learn more about adding accessibility features to your app, see [Accessibility-fundamentals](Accessibility-fundamentals.zh-Hans.md).

## Labels

- **accessibilityLabel(_:)**: Adds a label to the view that describes its contents.
- **accessibilityLabel(_:isEnabled:)**: Adds a label to the view that describes its contents.
- **accessibilityLabel(content:)**: Adds a label to the view that describes its contents.
- **accessibilityInputLabels(_:)**: Sets alternate input labels with which users identify a view.
- **accessibilityInputLabels(_:isEnabled:)**: Sets alternate input labels with which users identify a view.
- **accessibilityLabeledPair(role:id:in:)**: Pairs an accessibility element representing a label with the element for the matching content.

## Values

- **accessibilityValue(_:)**: Adds a textual description of the value that the view contains.
- **accessibilityValue(_:isEnabled:)**: Adds a textual description of the value that the view contains.

## Hints

- **accessibilityHint(_:)**: Communicates to the user what happens after performing the view’s action.
- **accessibilityHint(_:isEnabled:)**: Communicates to the user what happens after performing the view’s action.

## Actions

- **accessibilityAction(_:_:)**: Adds an accessibility action to the view. Actions allow assistive technologies, such as the VoiceOver, to interact with the view by invoking the action.
- **accessibilityActions(_:)**: Adds multiple accessibility actions to the view.
- **accessibilityAction(named:_:)**: Adds an accessibility action to the view. Actions allow assistive technologies, such as the VoiceOver, to interact with the view by invoking the action.
- **accessibilityAction(action:label:)**: Adds an accessibility action to the view. Actions allow assistive technologies, such as the VoiceOver, to interact with the view by invoking the action.
- **accessibilityAction(intent:label:)**: Adds an accessibility action labeled by the contents of `label` to the view. Actions allow assistive technologies, such as the VoiceOver, to interact with the view by invoking the action. When the action is performed, the `intent` will be invoked.
- **accessibilityAction(_:intent:)**: Adds an accessibility action representing `actionKind` to the view. Actions allow assistive technologies, such as the VoiceOver, to interact with the view by invoking the action. When the action is performed, the `intent` will be invoked.
- **accessibilityAction(named:intent:)**: Adds an accessibility action labeled `name` to the view. Actions allow assistive technologies, such as the VoiceOver, to interact with the view by invoking the action. When the action is performed, the `intent` will be invoked.
- **accessibilityAdjustableAction(_:)**: Adds an accessibility adjustable action to the view. Actions allow assistive technologies, such as the VoiceOver, to interact with the view by invoking the action.
- **accessibilityScrollAction(_:)**: Adds an accessibility scroll action to the view. Actions allow assistive technologies, such as the VoiceOver, to interact with the view by invoking the action.

## Gestures

- **accessibilityActivationPoint(_:)**: The activation point for an element is the location assistive technologies use to initiate gestures.
- **accessibilityActivationPoint(_:isEnabled:)**: The activation point for an element is the location assistive technologies use to initiate gestures.
- **accessibilityDragPoint(_:description:)**: The point an assistive technology should use to begin a drag interaction.
- **accessibilityDragPoint(_:description:isEnabled:)**: The point an assistive technology should use to begin a drag interaction.
- **accessibilityDropPoint(_:description:)**: The point an assistive technology should use to end a drag interaction.
- **accessibilityDropPoint(_:description:isEnabled:)**: The point an assistive technology should use to end a drag interaction.
- **accessibilityDirectTouch(_:options:)**: Explicitly set whether this accessibility element is a direct touch area. Direct touch areas passthrough touch events to the app rather than being handled through an assistive technology, such as VoiceOver. The modifier accepts an optional `AccessibilityDirectTouchOptions` option set to customize the functionality of the direct touch area.
- **accessibilityZoomAction(_:)**: Adds an accessibility zoom action to the view. Actions allow assistive technologies, such as VoiceOver, to interact with the view by invoking the action.

## Elements

- **accessibilityElement(children:)**: Creates a new accessibility element, or modifies the [AccessibilityChildBehavior](AccessibilityChildBehavior.zh-Hans.md) of the existing accessibility element.
- **accessibilityChildren(children:)**: Replaces the existing accessibility element’s children with one or more new synthetic accessibility elements.
- **accessibilityHidden(_:)**: Specifies whether to hide this view from system accessibility features.
- **accessibilityHidden(_:isEnabled:)**: Specifies whether to hide this view from system accessibility features.

## Custom controls

- **accessibilityRepresentation(representation:)**: Replaces one or more accessibility elements for this view with new accessibility elements.
- **accessibilityRespondsToUserInteraction(_:)**: Explicitly set whether this Accessibility element responds to user interaction and would thus be interacted with by technologies such as Switch Control, Voice Control or Full Keyboard Access.
- **accessibilityRespondsToUserInteraction(_:isEnabled:)**: Explicitly set whether this Accessibility element responds to user interaction and would thus be interacted with by technologies such as Switch Control, Voice Control or Full Keyboard Access.

## Custom content

- **accessibilityCustomContent(_:_:importance:)**: Add additional accessibility information to the view.

## Working with rotors

- **accessibilityRotor(_:entries:)**: Create an Accessibility Rotor with the specified user-visible label, and entries generated from the content closure.
- **accessibilityRotor(_:entries:entryID:entryLabel:)**: Create an Accessibility Rotor with the specified user-visible label and entries.
- **accessibilityRotor(_:entries:entryLabel:)**: Create an Accessibility Rotor with the specified user-visible label and entries.
- **accessibilityRotor(_:textRanges:)**: Create an Accessibility Rotor with the specified user-visible label and entries for each of the specified ranges. The Rotor will be attached to the current Accessibility element, and each entry will go the specified range of that element.

## Configuring rotors

- **accessibilityRotorEntry(id:in:)**: Defines an explicit identifier tying an Accessibility element for this view to an entry in an Accessibility Rotor.
- **accessibilityLinkedGroup(id:in:)**: Links multiple accessibility elements so that the user can quickly navigate from one element to another, even when the elements are not near each other in the accessibility hierarchy.
- **accessibilitySortPriority(_:)**: Sets the sort priority order for this view’s accessibility element, relative to other elements at the same level.

## Focus

- **accessibilityFocused(_:)**: Modifies this view by binding its accessibility element’s focus state to the given boolean state value.
- **accessibilityFocused(_:equals:)**: Modifies this view by binding its accessibility element’s focus state to the given state value.

## Traits

- **accessibilityAddTraits(_:)**: Adds the given traits to the view.
- **accessibilityRemoveTraits(_:)**: Removes the given traits from this view.

## Identity

- **accessibilityIdentifier(_:)**: Uses the string you specify to identify the view.
- **accessibilityIdentifier(_:isEnabled:)**: Uses the string you specify to identify the view.

## Color inversion

- **accessibilityIgnoresInvertColors(_:)**: Sets whether this view should ignore the system Smart Invert setting.

## Content descriptions

- **accessibilityTextContentType(_:)**: Sets an accessibility text content type.
- **accessibilityHeading(_:)**: Sets the accessibility level of this heading.

## VoiceOver

- **speechAdjustedPitch(_:)**: Raises or lowers the pitch of spoken text.
- **speechAlwaysIncludesPunctuation(_:)**: Sets whether VoiceOver should always speak all punctuation in the text view.
- **speechAnnouncementsQueued(_:)**: Controls whether to queue pending announcements behind existing speech rather than interrupting speech in progress.
- **speechSpellsOutCharacters(_:)**: Sets whether VoiceOver should speak the contents of the text view character by character.

## Charts

- **accessibilityChartDescriptor(_:)**: Adds a descriptor to a View that represents a chart to make the chart’s contents accessible to all users.

## Large content

- **accessibilityShowsLargeContentViewer()**: Adds a default large content view to be shown by the large content viewer.
- **accessibilityShowsLargeContentViewer(_:)**: Adds a custom large content view to be shown by the large content viewer.

## Quick actions

- **accessibilityQuickAction(style:content:)**: Adds a quick action to be shown by the system when active.
- **accessibilityQuickAction(style:isActive:content:)**: Adds a quick action to be shown by the system when active.

## Configuring view elements

- **Appearance modifiers**: Configure a view’s foreground and background styles, controls, and visibility.
- **Text and symbol modifiers**: Manage the rendering, selection, and entry of text in your view.
- **Auxiliary view modifiers**: Add and configure supporting views, like toolbars and context menus.
- **Chart view modifiers**: Configure charts that you declare with Swift Charts.

