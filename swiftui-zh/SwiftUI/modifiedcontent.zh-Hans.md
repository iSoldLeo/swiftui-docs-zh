--- 来源：https://developer.apple.com/documentation/swiftui/modifiedcontent
抓取时间：2025-12-02T17:47:19Z

---

# ModifiedContent

**Structure**

应用了修饰符的值。

## 声明

```swift
@frozen struct ModifiedContent<Content, Modifier>
```

## 创建修改后的内容视图

- **init(content:modifier:)**：定义生成新视图或视图修饰符所需的内容和修饰符的结构。

- **content**：修饰符转换为新视图或新视图修饰符的内容。

- **modifier**：视图修饰符。

## 实例方法

- **accessibility(activationPoint:)**：指定视图中发生激活的位置。

- **accessibility(addTraits:)**：向视图添加指定的特性。

- **accessibility(hidden:)**：指定是否从系统辅助功能中隐藏此视图。

- **accessibility(hint:)**：告知用户执行视图操作后会发生什么。

- **accessibility(identifier:)**：使用指定的字符串标识视图。

- **accessibility(inputLabels:)**：设置用户用于标识视图的备用输入标签。

- **accessibility(label:)**：向视图添加描述其内容的标签。

- **accessibility(removeTraits:)**：从此视图中移除指定的特性。

- **accessibility(selectionIdentifier:)**：为此视图的辅助功能元素设置选择标识符。

- **accessibility(sortPriority:)**：设置此视图辅助功能元素相对于同一级别其他元素的排序优先级。

- **accessibility(value:)**：添加视图所包含值的文本描述。

- **accessibilityAction(_:_:)**：向视图添加辅助功能操作。操作允许 VoiceOver 等辅助技术通过调用该操作与视图进行交互。

- **accessibilityAction(_:intent:)**：向视图添加代表 `actionKind` 的辅助功能操作。操作允许 VoiceOver 等辅助技术通过调用该操作与视图进行交互。执行该操作时，将调用 `intent`。

- **accessibilityAction(named:_:)**：向视图添加辅助功能操作。操作允许 VoiceOver 等辅助技术通过调用该操作与视图进行交互。

- **accessibilityAction(named:intent:)**：向视图添加一个名为 `name` 的辅助功能操作。操作允许 VoiceOver 等辅助技术通过调用该操作与视图进行交互。执行该操作时，将调用 `intent`。

- **accessibilityActivationPoint(_:)**：元素的激活点是辅助技术用于启动手势的位置。

- **accessibilityActivationPoint(_:isEnabled:)**：元素的激活点是辅助技术用于启动手势的位置。

- **accessibilityAddTraits(_:)**：向视图添加指定的特性。

- **accessibilityAdjustableAction(_:)**：向视图添加一个可调整的辅助功能操作。操作允许辅助技术（例如 VoiceOver）通过调用操作与视图进行交互。

- **accessibilityCustomContent(_:_:importance:)**：向视图添加其他辅助功能信息。

- **accessibilityDirectTouch(_:options:)**：显式设置此辅助功能元素是否为直接触摸区域。直接触摸区域会将触摸事件传递给应用程序，而不是通过辅助技术（例如 VoiceOver）处理。此修饰符接受一个可选的 `AccessibilityDirectTouchOptions` 选项集，用于自定义直接触摸区域的功能。

- **accessibilityDragPoint(_:description:)**：辅助技术开始拖动交互的点。

- **accessibilityDragPoint(_:description:isEnabled:)**：辅助技术开始拖动交互的点。

- **accessibilityDropPoint(_:description:)**：辅助技术结束拖动交互的点。

- **accessibilityDropPoint(_:description:isEnabled:)**：辅助技术结束拖拽交互的点。

- **accessibilityHeading(_:)**：设置此标题的级别。

- **accessibilityHidden(_:)**：指定是否从系统辅助功能中隐藏此视图。

- **accessibilityHidden(_:isEnabled:)**：指定是否从系统辅助功能中隐藏此视图。

- **accessibilityHint(_:)**：向用户说明执行视图操作后会发生什么。

- **accessibilityHint(_:isEnabled:)**：向用户说明执行视图操作后会发生什么。

- **accessibilityIdentifier(_:)**：使用您指定的字符串来标识视图。

- **accessibilityIdentifier(_:isEnabled:)**：使用您指定的字符串来标识视图。

- **accessibilityInputLabels(_:)**：设置用户用于识别视图的备用输入标签。

- **accessibilityInputLabels(_:isEnabled:)**：设置用户用于识别视图的备用输入标签。

- **accessibilityLabel(_:)**：向视图添加描述其内容的标签。

- **accessibilityLabel(_:isEnabled:)**：向视图添加描述其内容的标签。

- **accessibilityRemoveTraits(_:)**：从该视图中移除指定的属性。

- **accessibilityRespondsToUserInteraction(_:)**：显式设置此辅助功能元素是否响应用户交互，从而是否可通过切换控制、语音控制或全键盘访问等技术进行交互。

- **accessibilityRespondsToUserInteraction(_:isEnabled:)**：显式设置此辅助功能元素是否响应用户交互，从而是否可通过切换控制、语音控制或全键盘访问等技术进行交互。

- **accessibilityScrollAction(_:)**：为视图添加辅助功能滚动操作。操作允许 VoiceOver 等辅助技术通过调用该操作与视图进行交互。

- **accessibilityScrollStatus(_:isEnabled:)**：更改用户在此视图内滚动其他滚动视图时辅助功能技术提供的语音提示。

- **accessibilitySortPriority(_:)**：设置此视图辅助功能元素相对于同一级别其他元素的排序优先级。

- **accessibilityTextContentType(_:)**：设置辅助功能文本内容类型。

- **accessibilityValue(_:)**：添加视图所包含值的文本描述。

- **accessibilityValue(_:isEnabled:)**：添加视图所包含值的文本描述。

- **accessibilityZoomAction(_:)**：为视图添加辅助功能缩放操作。操作允许 VoiceOver 等辅助技术通过调用操作与视图进行交互。

## 修改视图

- **配置视图**：通过应用视图修饰符来调整视图的特性。

- **减少视图修饰符的维护**：将经常重复使用的视图修饰符打包成一个自定义视图修饰符。

- **modifier(_:)**：将修饰符应用于视图并返回一个新视图。

- **ViewModifier**：应用于视图或其他视图修饰符的修饰符，生成原始值的不同版本。

- **EmptyModifier**：一个空修饰符（或标识修饰符），用于在开发过程中在编译时切换修饰符。

- **EnvironmentalModifier**：必须在使用前解析为环境中的具体修饰符的修饰符。

- **ManipulableModifier**

- **ManipulableResponderModifier**

- **ManipulableTransformBindingModifier**

- **ManipulationGeometryModifier**

- **ManipulationGestureModifier**

- **ManipulationUsingGestureStateModifier**

- **Manipulable**：一个用于各种可操作相关类型的命名空间。

## 符合以下规范

- Animatable

- Chart3DContent

- Copyable

- CustomHoverEffect

- DynamicMapContent

- DynamicTableRowContent

- DynamicViewContent

- Equatable

- HoverEffectContent

- MapContent

- Scene

- Sendable

- SendableMetatype

- TableRowContent

- View

- ViewModifier

- VisualEffect


---
source: https://developer.apple.com/documentation/swiftui/modifiedcontent
crawled: 2025-12-02T17:47:19Z
---

# ModifiedContent

**Structure**

A value with a modifier applied to it.

## Declaration

```swift
@frozen struct ModifiedContent<Content, Modifier>
```

## Creating a modified content view

- **init(content:modifier:)**: A structure that defines the content and modifier needed to produce a new view or view modifier.
- **content**: The content that the modifier transforms into a new view or new view modifier.
- **modifier**: The view modifier.

## Instance Methods

- **accessibility(activationPoint:)**: Specifies the point where activations occur in the view.
- **accessibility(addTraits:)**: Adds the given traits to the view.
- **accessibility(hidden:)**: Specifies whether to hide this view from system accessibility features.
- **accessibility(hint:)**: Communicates to the user what happens after performing the view’s action.
- **accessibility(identifier:)**: Uses the specified string to identify the view.
- **accessibility(inputLabels:)**: Sets alternate input labels with which users identify a view.
- **accessibility(label:)**: Adds a label to the view that describes its contents.
- **accessibility(removeTraits:)**: Removes the given traits from this view.
- **accessibility(selectionIdentifier:)**: Sets a selection identifier for this view’s accessibility element.
- **accessibility(sortPriority:)**: Sets the sort priority order for this view’s accessibility element, relative to other elements at the same level.
- **accessibility(value:)**: Adds a textual description of the value that the view contains.
- **accessibilityAction(_:_:)**: Adds an accessibility action to the view. Actions allow assistive technologies, such as the VoiceOver, to interact with the view by invoking the action.
- **accessibilityAction(_:intent:)**: Adds an accessibility action representing `actionKind` to the view. Actions allow assistive technologies, such as the VoiceOver, to interact with the view by invoking the action. When the action is performed, the `intent` will be invoked.
- **accessibilityAction(named:_:)**: Adds an accessibility action to the view. Actions allow assistive technologies, such as the VoiceOver, to interact with the view by invoking the action.
- **accessibilityAction(named:intent:)**: Adds an accessibility action labeled `name` to the view. Actions allow assistive technologies, such as the VoiceOver, to interact with the view by invoking the action. When the action is performed, the `intent` will be invoked.
- **accessibilityActivationPoint(_:)**: The activation point for an element is the location assistive technologies use to initiate gestures.
- **accessibilityActivationPoint(_:isEnabled:)**: The activation point for an element is the location assistive technologies use to initiate gestures.
- **accessibilityAddTraits(_:)**: Adds the given traits to the view.
- **accessibilityAdjustableAction(_:)**: Adds an accessibility adjustable action to the view. Actions allow assistive technologies, such as the VoiceOver, to interact with the view by invoking the action.
- **accessibilityCustomContent(_:_:importance:)**: Add additional accessibility information to the view.
- **accessibilityDirectTouch(_:options:)**: Explicitly set whether this accessibility element is a direct touch area. Direct touch areas passthrough touch events to the app rather than being handled through an assistive technology, such as VoiceOver. The modifier accepts an optional `AccessibilityDirectTouchOptions` option set to customize the functionality of the direct touch area.
- **accessibilityDragPoint(_:description:)**: The point an assistive technology should use to begin a drag interaction.
- **accessibilityDragPoint(_:description:isEnabled:)**: The point an assistive technology should use to begin a drag interaction.
- **accessibilityDropPoint(_:description:)**: The point an assistive technology should use to end a drag interaction.
- **accessibilityDropPoint(_:description:isEnabled:)**: The point an assistive technology should use to end a drag interaction.
- **accessibilityHeading(_:)**: Set the level of this heading.
- **accessibilityHidden(_:)**: Specifies whether to hide this view from system accessibility features.
- **accessibilityHidden(_:isEnabled:)**: Specifies whether to hide this view from system accessibility features.
- **accessibilityHint(_:)**: Communicates to the user what happens after performing the view’s action.
- **accessibilityHint(_:isEnabled:)**: Communicates to the user what happens after performing the view’s action.
- **accessibilityIdentifier(_:)**: Uses the string you specify to identify the view.
- **accessibilityIdentifier(_:isEnabled:)**: Uses the string you specify to identify the view.
- **accessibilityInputLabels(_:)**: Sets alternate input labels with which users identify a view.
- **accessibilityInputLabels(_:isEnabled:)**: Sets alternate input labels with which users identify a view.
- **accessibilityLabel(_:)**: Adds a label to the view that describes its contents.
- **accessibilityLabel(_:isEnabled:)**: Adds a label to the view that describes its contents.
- **accessibilityRemoveTraits(_:)**: Removes the given traits from this view.
- **accessibilityRespondsToUserInteraction(_:)**: Explicitly set whether this Accessibility element responds to user interaction and would thus be interacted with by technologies such as Switch Control, Voice Control or Full Keyboard Access.
- **accessibilityRespondsToUserInteraction(_:isEnabled:)**: Explicitly set whether this Accessibility element responds to user interaction and would thus be interacted with by technologies such as Switch Control, Voice Control or Full Keyboard Access.
- **accessibilityScrollAction(_:)**: Adds an accessibility scroll action to the view. Actions allow assistive technologies, such as the VoiceOver, to interact with the view by invoking the action.
- **accessibilityScrollStatus(_:isEnabled:)**: Changes the announcement provided by accessibility technologies when a user scrolls a scroll view within this view.
- **accessibilitySortPriority(_:)**: Sets the sort priority order for this view’s accessibility element, relative to other elements at the same level.
- **accessibilityTextContentType(_:)**: Sets an accessibility text content type.
- **accessibilityValue(_:)**: Adds a textual description of the value that the view contains.
- **accessibilityValue(_:isEnabled:)**: Adds a textual description of the value that the view contains.
- **accessibilityZoomAction(_:)**: Adds an accessibility zoom action to the view. Actions allow assistive technologies, such as VoiceOver, to interact with the view by invoking the action.

## Modifying a view

- **Configuring views**: Adjust the characteristics of a view by applying view modifiers.
- **Reducing view modifier maintenance**: Bundle view modifiers that you regularly reuse into a custom view modifier.
- **modifier(_:)**: Applies a modifier to a view and returns a new view.
- **ViewModifier**: A modifier that you apply to a view or another view modifier, producing a different version of the original value.
- **EmptyModifier**: An empty, or identity, modifier, used during development to switch modifiers at compile time.
- **EnvironmentalModifier**: A modifier that must resolve to a concrete modifier in an environment before use.
- **ManipulableModifier**
- **ManipulableResponderModifier**
- **ManipulableTransformBindingModifier**
- **ManipulationGeometryModifier**
- **ManipulationGestureModifier**
- **ManipulationUsingGestureStateModifier**
- **Manipulable**: A namespace for various manipulable related types.

## Conforms To

- Animatable
- Chart3DContent
- Copyable
- CustomHoverEffect
- DynamicMapContent
- DynamicTableRowContent
- DynamicViewContent
- Equatable
- HoverEffectContent
- MapContent
- Scene
- Sendable
- SendableMetatype
- TableRowContent
- View
- ViewModifier
- VisualEffect

