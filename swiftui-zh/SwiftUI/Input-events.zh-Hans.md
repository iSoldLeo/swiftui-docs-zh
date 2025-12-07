--- 来源：https://developer.apple.com/documentation/SwiftUI/Input-events
抓取时间：2025-12-02T17:41:24Z

---

# 输入事件

**API 集合**

响应来自硬件设备（例如键盘或触控栏）的输入。

## 概述

SwiftUI 提供视图修饰符，使您的应用能够监听并响应各种类型的用户输入。例如，您可以创建键盘快捷键、响应表单提交或从 Apple Watch 的数码表冠获取输入。

有关设计指南，请参阅《人机界面指南》中的 [doc://com.apple.documentation/design/Human-Interface-Guidelines/inputs]。

## 响应键盘输入

- **onKeyPress(_:action:)**：当用户在视图获得焦点时按下硬件键盘上的键，则执行相应的操作。

- **onKeyPress(phases:action:)**：当视图获得焦点时，如果用户按下硬件键盘上的任意键，则执行此操作。

- **onKeyPress(_:phases:action:)**：当视图获得焦点时，如果用户按下硬件键盘上的某个键，则执行此操作。

- **onKeyPress(characters:phases:action:)**：当视图获得焦点时，如果用户按下硬件键盘上的一个或多个键，则执行此操作。

- **onKeyPress(keys:phases:action:)**：当视图获得焦点时，如果用户按下硬件键盘上的一个或多个键，则执行此操作。

- **KeyPress**

## 创建键盘快捷键

- **keyboardShortcut(_:)**：为修改后的控件分配键盘快捷键。

- **keyboardShortcut(_:modifiers:)**：定义键盘快捷键并将其分配给修改后的控件。

- **keyboardShortcut(_:modifiers:localization:)**：定义键盘快捷键并将其分配给修改后的控件。

- **keyboardShortcut**：此环境中按钮的触发快捷键。

- **KeyboardShortcut**：键盘快捷键描述了用户按下键盘上的组合键，以激活按钮或切换开关。

- **KeyEquivalent**：按键等效项由字母、标点符号或功能键组成，可以与一组可选的修饰键组合使用，以指定键盘快捷键。

- **EventModifiers**：可以添加到手势的一组修饰键。

## 响应修饰键

- **onModifierKeysChanged(mask:initial:_:)**：当用户按下或释放硬件修饰键时执行操作。

- **modifierKeyAlternate(_:_:)**：当用户按下指定组合的修饰键时，创建一个视图来替换已修改的视图。

## 响应悬停事件

- **onHover(perform:)**：添加一个操作，当用户将指针移到视图框架上方或下方时执行。

- **onContinuousHover(coordinateSpace:perform:)**：添加一个操作，当指针进入、移动到视图边界内以及离开视图边界时执行。

- **hoverEffect(_:isEnabled:)**：为该视图应用悬停效果。

- **hoverEffectDisabled(_:)**：添加一个条件，用于控制该视图是否可以显示悬停效果。

- **defaultHoverEffect(_:)**：设置该视图内其他视图使用的默认悬停效果。

- **isHoverEffectEnabled**：一个布尔值，指示与此环境关联的视图是否允许显示悬停效果。

- **HoverPhase**：指针的当前悬停状态和值。

- **HoverEffectPhaseOverride**：用于覆盖悬停效果当前阶段的选项。

- **OrnamentHoverContentEffect**：使用自定义效果在悬停时显示装饰物。

- **OrnamentHoverEffect**：在悬停时显示装饰物。

## 修改指针外观

- **pointerStyle(_:)**：设置指针悬停在视图上时显示的指针样式。

- **PointerStyle**：描述指针（也称为光标）悬停在视图上时的外观的样式。

- **pointerVisibility(_:)**：设置指针悬停在视图上时的可见性。

## 更改悬停事件的视图外观

- **hoverEffect(_:)**：为该视图应用悬停效果。

- **HoverEffect**：指针悬停在视图上时应用的效果。

- **hoverEffect(_:in:isEnabled:)**：为该视图应用悬停效果，并可选择将其添加到 [HoverEffectGroup](HoverEffectGroup.zh-Hans.md)。

- **hoverEffect(in:isEnabled:body:)**：为该视图应用由给定闭包描述的悬停效果。

- **CustomHoverEffect**：一种类型，表示当指针悬停在视图上或有人查看视图时，视图应如何变化。

- **ContentHoverEffect**：一个使用闭包在鼠标悬停时对视图应用效果的 `CustomHoverEffect`。

- **HoverEffectGroup**：描述一组同时激活的效果。

- **hoverEffectGroup()**：为所有在子视图上定义的效果添加一个隐式的 [HoverEffectGroup](HoverEffectGroup.zh-Hans.md)，以便在鼠标悬停于此视图或任何子视图时，添加到子视图的所有效果作为一个组激活。

- **hoverEffectGroup(_:)**：为所有在子视图上定义的效果添加一个 [HoverEffectGroup](HoverEffectGroup.zh-Hans.md)，并在鼠标悬停于此视图或任何子视图时激活该组效果。

- **hoverEffectGroup(id:in:behavior:)**：向所有子视图上定义的效果添加一个 [HoverEffectGroup](HoverEffectGroup.zh-Hans.md)，并在鼠标悬停于此视图或任何子视图上时激活该效果组。

- **GroupHoverEffect**：一个 `CustomHoverEffect`，用于激活一个已命名的效果组。

- **HoverEffectContent**：一种类型，用于描述视图在特定悬停效果阶段的效果。

- **EmptyHoverEffectContent**：一个空的基础效果，可用于构建其他效果。

- **handPointerBehavior(_:)**：设置用户与视图交互时手形指针的行为。

- **HandPointerBehavior**：一种可在用户与视图交互时应用于手形指针的行为。

## 响应提交事件

- **onSubmit(of:_:)**：添加用户向此视图提交值时要执行的操作。

- **submitScope(_:)**：阻止源自此视图的提交触发器调用视图层次结构中更高层级提交修饰符配置的提交操作。

- **SubmitTriggers**：定义各种触发提交操作的触发器的类型。

## 标记提交事件

- **submitLabel(_:)**：设置此视图的提交标签。

- **SubmitLabel**：描述视图层次结构中提交标签的语义标签。

## 响应命令

- **onMoveCommand(perform:)**：添加一个操作，用于响应移动命令，例如用户按下 Mac 键盘上的方向键，或在控制 Apple TV 时轻点 Siri Remote 的边缘。

- **onDeleteCommand(perform:)**：添加一个操作，用于响应系统的删除命令，或在视图获得焦点时按下 ⌫（退格键）或 ⌦（向前删除键）。

- **pageCommand(value:in:step:)**：响应 Page Up 或 Page Down 命令，使值在指定范围内逐级递增。

- **onExitCommand(perform:)**：设置一个操作，用于在视图获得焦点时，响应接收到退出命令而触发。

- **onPlayPauseCommand(perform:)**：添加一个操作，用于响应系统的播放/暂停命令。

- **onCommand(_:perform:)**：添加响应给定选择器而执行的操作。

- **MoveCommandDirection**：指定方向键的移动方向。

## 控制命中测试

- **allowsTightening(_:)**：设置此视图中的文本是否可以在必要时压缩字符间距以适应一行。

- **contentShape(_:eoFill:)**：定义命中测试的内容形状。

- **contentShape(_:_:eoFill:)**：设置此视图的内容形状。

- **ContentShapeKinds**：视图内容形状的类型。

## 与数码表冠交互

- **digitalCrownAccessory(_:)**：指定 Apple Watch 上数码表冠配件视图的可见性。

- **digitalCrownAccessory(content:)**：在 Apple Watch 的数码表冠旁边放置一个配件视图。

- **digitalCrownRotation(_:from:through:sensitivity:isContinuous:isHapticFeedbackEnabled:onChange:onIdle:)**：通过更新指定的绑定来跟踪数码表冠的旋转。

- **digitalCrownRotation(_:onChange:onIdle:)**：通过更新指定的绑定来跟踪数码表冠的旋转。

- **digitalCrownRotation(detent:from:through:by:sensitivity:isContinuous:isHapticFeedbackEnabled:onChange:onIdle:)**：通过更新指定的绑定来跟踪数码表冠的旋转。

- **digitalCrownRotation(_:)**：通过更新指定的绑定来跟踪数码表冠的旋转。

- **digitalCrownRotation(_:from:through:by:sensitivity:isContinuous:isHapticFeedbackEnabled:)**：通过更新指定的绑定来跟踪数码表冠的旋转。

- **DigitalCrownEvent**：用户旋转数码表冠时触发的事件。

- **DigitalCrownRotationalSensitivity**：在两个整数之间移动所需的数码表冠旋转量。

## 管理触控栏输入

- **touchBar(content:)**：设置触控栏显示的内容。

- **touchBar(_:)**：设置触控栏在适用时显示的内容。

- **touchBarItemPrincipal(_:)**：设置对该触控栏具有特殊意义的主要视图。

- **touchBarCustomizationLabel(_:)**：设置一个用户可见的字符串，用于标识视图的功能。

- **touchBarItemPresence(_:)**：设置用户自定义视图的行为。

- **TouchBar**：用于在触控栏中显示的视图的容器。

- **TouchBarItemPresence**：影响用户自定义触控栏的选项。

## 响应捕获事件

- **onCameraCaptureEvent(isEnabled:action:)**：用于注册由系统捕获事件触发的操作。

- **onCameraCaptureEvent(isEnabled:primaryAction:secondaryAction:)**：用于注册由系统捕获事件触发的操作。

## 事件处理

- **Gestures**：定义从点击、轻触、滑动到更精细的手势等各种交互方式。

- **Clipboard**：允许用户通过发出复制和粘贴命令来移动或复制项目。

- **拖放**：允许用户通过将项目从一个位置拖动到另一个位置来移动或复制项目。

- **Focus**：识别并控制哪些可见对象响应用户交互。

- **系统事件**：响应系统事件，例如打开 URL。


---
source: https://developer.apple.com/documentation/SwiftUI/Input-events
crawled: 2025-12-02T17:41:24Z
---

# Input events

**API Collection**

Respond to input from a hardware device, like a keyboard or a Touch Bar.

## Overview

SwiftUI provides view modifiers that enable your app to listen for and react to various kinds of user input. For example, you can create keyboard shortcuts, respond to a form submission, or take input from the digital crown of an Apple Watch.



For design guidance, see [doc://com.apple.documentation/design/Human-Interface-Guidelines/inputs] in the Human Interface Guidelines.

## Responding to keyboard input

- **onKeyPress(_:action:)**: Performs an action if the user presses a key on a hardware keyboard while the view has focus.
- **onKeyPress(phases:action:)**: Performs an action if the user presses any key on a hardware keyboard while the view has focus.
- **onKeyPress(_:phases:action:)**: Performs an action if the user presses a key on a hardware keyboard while the view has focus.
- **onKeyPress(characters:phases:action:)**: Performs an action if the user presses one or more keys on a hardware keyboard while the view has focus.
- **onKeyPress(keys:phases:action:)**: Performs an action if the user presses one or more keys on a hardware keyboard while the view has focus.
- **KeyPress**

## Creating keyboard shortcuts

- **keyboardShortcut(_:)**: Assigns a keyboard shortcut to the modified control.
- **keyboardShortcut(_:modifiers:)**: Defines a keyboard shortcut and assigns it to the modified control.
- **keyboardShortcut(_:modifiers:localization:)**: Defines a keyboard shortcut and assigns it to the modified control.
- **keyboardShortcut**: The keyboard shortcut that buttons in this environment will be triggered with.
- **KeyboardShortcut**: Keyboard shortcuts describe combinations of keys on a keyboard that the user can press in order to activate a button or toggle.
- **KeyEquivalent**: Key equivalents consist of a letter, punctuation, or function key that can be combined with an optional set of modifier keys to specify a keyboard shortcut.
- **EventModifiers**: A set of key modifiers that you can add to a gesture.

## Responding to modifier keys

- **onModifierKeysChanged(mask:initial:_:)**: Performs an action whenever the user presses or releases a hardware modifier key.
- **modifierKeyAlternate(_:_:)**: Builds a view to use in place of the modified view when the user presses the modifier key(s) indicated by the given set.

## Responding to hover events

- **onHover(perform:)**: Adds an action to perform when the user moves the pointer over or away from the view’s frame.
- **onContinuousHover(coordinateSpace:perform:)**: Adds an action to perform when the pointer enters, moves within, and exits the view’s bounds.
- **hoverEffect(_:isEnabled:)**: Applies a hover effect to this view.
- **hoverEffectDisabled(_:)**: Adds a condition that controls whether this view can display hover effects.
- **defaultHoverEffect(_:)**: Sets the default hover effect to use for views within this view.
- **isHoverEffectEnabled**: A Boolean value that indicates whether the view associated with this environment allows hover effects to be displayed.
- **HoverPhase**: The current hovering state and value of the pointer.
- **HoverEffectPhaseOverride**: Options for overriding a hover effect’s current phase.
- **OrnamentHoverContentEffect**: Presents an ornament on hover using a custom effect.
- **OrnamentHoverEffect**: Presents an ornament on hover.

## Modifying pointer appearance

- **pointerStyle(_:)**: Sets the pointer style to display when the pointer is over the view.
- **PointerStyle**: A style describing the appearance of the pointer (also called a cursor) when it’s hovered over a view.
- **pointerVisibility(_:)**: Sets the visibility of the pointer when it’s over the view.

## Changing view appearance for hover events

- **hoverEffect(_:)**: Applies a hover effect to this view.
- **HoverEffect**: An effect applied when the pointer hovers over a view.
- **hoverEffect(_:in:isEnabled:)**: Applies a hover effect to this view, optionally adding it to a [HoverEffectGroup](HoverEffectGroup.zh-Hans.md).
- **hoverEffect(in:isEnabled:body:)**: Applies a hover effect to this view described by the given closure.
- **CustomHoverEffect**: A type that represents how a view should change when a pointer hovers over a view, or when someone looks at the view.
- **ContentHoverEffect**: A `CustomHoverEffect` that applies effects to a view on hover using a closure.
- **HoverEffectGroup**: Describes a grouping of effects that activate together.
- **hoverEffectGroup()**: Adds an implicit [HoverEffectGroup](HoverEffectGroup.zh-Hans.md) to all effects defined on descendant views, so that all effects added to subviews activate as a group whenever this view or any descendant views are hovered.
- **hoverEffectGroup(_:)**: Adds a [HoverEffectGroup](HoverEffectGroup.zh-Hans.md) to all effects defined on descendant views, and activates the group whenever this view or any descendant views are hovered.
- **hoverEffectGroup(id:in:behavior:)**: Adds a [HoverEffectGroup](HoverEffectGroup.zh-Hans.md) to all effects defined on descendant views, and activates the group whenever this view or any descendant views are hovered.
- **GroupHoverEffect**: A `CustomHoverEffect` that activates a named group of effects.
- **HoverEffectContent**: A type that describes the effects of a view for a particular hover effect phase.
- **EmptyHoverEffectContent**: An empty base effect that you use to build other effects.
- **handPointerBehavior(_:)**: Sets the behavior of the hand pointer while the user is interacting with the view.
- **HandPointerBehavior**: A behavior that can be applied to the hand pointer while the user is interacting with a view.

## Responding to submission events

- **onSubmit(of:_:)**: Adds an action to perform when the user submits a value to this view.
- **submitScope(_:)**: Prevents submission triggers originating from this view to invoke a submission action configured by a submission modifier higher up in the view hierarchy.
- **SubmitTriggers**: A type that defines various triggers that result in the firing of a submission action.

## Labeling a submission event

- **submitLabel(_:)**: Sets the submit label for this view.
- **SubmitLabel**: A semantic label describing the label of submission within a view hierarchy.

## Responding to commands

- **onMoveCommand(perform:)**: Adds an action to perform in response to a move command, like when the user presses an arrow key on a Mac keyboard, or taps the edge of the Siri Remote when controlling an Apple TV.
- **onDeleteCommand(perform:)**: Adds an action to perform in response to the system’s Delete command, or pressing either the ⌫ (backspace) or ⌦ (forward delete) keys while the view has focus.
- **pageCommand(value:in:step:)**: Steps a value through a range in response to page up or page down commands.
- **onExitCommand(perform:)**: Sets up an action that triggers in response to receiving the exit command while the view has focus.
- **onPlayPauseCommand(perform:)**: Adds an action to perform in response to the system’s Play/Pause command.
- **onCommand(_:perform:)**: Adds an action to perform in response to the given selector.
- **MoveCommandDirection**: Specifies the direction of an arrow key movement.

## Controlling hit testing

- **allowsTightening(_:)**: Sets whether text in this view can compress the space between characters when necessary to fit text in a line.
- **contentShape(_:eoFill:)**: Defines the content shape for hit testing.
- **contentShape(_:_:eoFill:)**: Sets the content shape for this view.
- **ContentShapeKinds**: A kind for the content shape of a view.

## Interacting with the Digital Crown

- **digitalCrownAccessory(_:)**: Specifies the visibility of Digital Crown accessory Views on Apple Watch.
- **digitalCrownAccessory(content:)**: Places an accessory View next to the Digital Crown on Apple Watch.
- **digitalCrownRotation(_:from:through:sensitivity:isContinuous:isHapticFeedbackEnabled:onChange:onIdle:)**: Tracks Digital Crown rotations by updating the specified binding.
- **digitalCrownRotation(_:onChange:onIdle:)**: Tracks Digital Crown rotations by updating the specified binding.
- **digitalCrownRotation(detent:from:through:by:sensitivity:isContinuous:isHapticFeedbackEnabled:onChange:onIdle:)**: Tracks Digital Crown rotations by updating the specified binding.
- **digitalCrownRotation(_:)**: Tracks Digital Crown rotations by updating the specified binding.
- **digitalCrownRotation(_:from:through:by:sensitivity:isContinuous:isHapticFeedbackEnabled:)**: Tracks Digital Crown rotations by updating the specified binding.
- **DigitalCrownEvent**: An event emitted when the user rotates the Digital Crown.
- **DigitalCrownRotationalSensitivity**: The amount of Digital Crown rotation needed to move between two integer numbers.

## Managing Touch Bar input

- **touchBar(content:)**: Sets the content that the Touch Bar displays.
- **touchBar(_:)**: Sets the Touch Bar content to be shown in the Touch Bar when applicable.
- **touchBarItemPrincipal(_:)**: Sets principal views that have special significance to this Touch Bar.
- **touchBarCustomizationLabel(_:)**: Sets a user-visible string that identifies the view’s functionality.
- **touchBarItemPresence(_:)**: Sets the behavior of the user-customized view.
- **TouchBar**: A container for a view that you can show in the Touch Bar.
- **TouchBarItemPresence**: Options that affect user customization of the Touch Bar.

## Responding to capture events

- **onCameraCaptureEvent(isEnabled:action:)**: Used to register an action triggered by system capture events.
- **onCameraCaptureEvent(isEnabled:primaryAction:secondaryAction:)**: Used to register actions triggered by system capture events.

## Event handling

- **Gestures**: Define interactions from taps, clicks, and swipes to fine-grained gestures.
- **Clipboard**: Enable people to move or duplicate items by issuing Copy and Paste commands.
- **Drag and drop**: Enable people to move or duplicate items by dragging them from one location to another.
- **Focus**: Identify and control which visible object responds to user interaction.
- **System events**: React to system events, like opening a URL.

