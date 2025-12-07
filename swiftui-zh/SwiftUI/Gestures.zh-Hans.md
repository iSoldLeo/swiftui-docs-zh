---

来源：https://developer.apple.com/documentation/SwiftUI/Gestures
抓取时间：2025-12-02T17:42:32Z

---

# 手势

**API 集合**

定义从轻点、点击和滑动到更精细的手势交互。

## 概述

通过向视图添加手势修饰符来响应手势。您可以监听轻点、拖动、捏合和其他标准手势。

您还可以使用 [simultaneously(with:)](Gesture/simultaneously_with.zh-Hans.md)、[sequenced(before:)](Gesture/sequenced_before.zh-Hans.md) 或 [exclusively(before:)](Gesture/exclusively_before.zh-Hans.md) 修饰符将单个手势组合成自定义手势，或者使用 [modifiers(_:)](Gesture/modifiers.zh-Hans.md) 修饰符将手势与键盘修饰键结合使用。

设计指南请参见《人机界面指南》中的 [doc://com.apple.documentation/design/Human-Interface-Guidelines/gestures]。

## 基本功能

- **使用手势添加交互功能**：使用手势修饰符为您的应用添加交互功能。

## 识别点击手势

- **onTapGesture(count:perform:)**：添加一个操作，当此视图识别到点击手势时执行该操作。

- **onTapGesture(count:coordinateSpace:perform:)**：添加一个操作，当此视图识别到点击手势时执行该操作，并向该操作提供交互位置信息。

- **TapGesture**：一个可以识别一次或多次点击的手势。

- **SpatialTapGesture**：一个可以识别一次或多次点击并报告其位置的手势。

## 识别长按手势

- **onLongPressGesture(minimumDuration:maximumDistance:perform:onPressingChanged:)**：当此视图识别到长按手势时，添加要执行的操作。

- **onLongPressGesture(minimumDuration:perform:onPressingChanged:)**：当此视图识别到长按手势时，添加要执行的操作。

- **onLongTouchGesture(minimumDuration:perform:onTouchingChanged:)**：当此视图识别到远程长触手势时，添加要执行的操作。长触手势是指手指放在远程触控表面上但未实际按压。

- **LongPressGesture**：用户执行长按操作时成功的手势。

## 识别空间事件

- **SpatialEventGesture**：提供有关正在进行的空间事件（例如点击和触摸）信息的手势。

- **SpatialEventCollection**：针对特定视图的空间输入事件集合。

- **Chirality**：姿势的手性或惯用手。

## 识别随时间变化的手势

- **gesture(_:)**：将 [NSGestureRecognizerRepresentable](NSGestureRecognizerRepresentable.zh-Hans.md) 附加到视图。

- **gesture(_:isEnabled:)**：将一个手势附加到视图，其优先级低于视图定义的手势。

- **gesture(_:name:isEnabled:)**：将一个手势附加到视图，其优先级低于视图定义的手势。

- **gesture(_:including:)**：将一个手势附加到视图，其优先级低于视图定义的手势。

- **DragGesture**：拖动动作，当拖动事件序列发生变化时，会触发相应的操作。

- **WindowDragGesture**：一种识别并处理窗口拖动的手势。

- **MagnifyGesture**：一种识别放大手势并跟踪放大倍数的手势。

- **RotateGesture**：一种识别旋转手势并跟踪旋转角度的手势。

- **RotateGesture3D**：一种识别 3D 旋转手势并跟踪旋转角度和轴的手势。

- **GestureMask**：用于控制向视图添加手势如何影响该视图及其子视图识别的其他手势的选项。

## 识别 Apple Pencil 手势

- **onPencilDoubleTap(perform:)**：添加用户双击 Apple Pencil 后要执行的操作。

- **onPencilSqueeze(perform:)**：添加用户挤压 Apple Pencil 时要执行的操作。

- **preferredPencilDoubleTapAction**：用户在“设置”应用中选择的，在双击 Apple Pencil 后首选执行的操作。

- **preferredPencilSqueezeAction**：用户在“设置”应用中选择的，在挤压 Apple Pencil 时首选执行的操作。

- **PencilPreferredAction**：用户在双击 Apple Pencil 后首选执行的操作。

- **PencilDoubleTapGestureValue**：描述 Apple Pencil 双击手势的价值。

- **PencilSqueezeGestureValue**：描述 Apple Pencil 挤压手势的价值。

- **PencilSqueezeGesturePhase**：描述 Apple Pencil 挤压手势的阶段和值。

- **PencilHoverPose**：描述 Apple Pencil 悬停在视图边界上方区域的位置和距离的值。

## 组合手势

- **组合 SwiftUI 手势**：组合手势以创建复杂的交互。

- **simultaneousGesture(_:including:)**：将手势附加到视图，以便与视图定义的其他手势同时处理。

- **simultaneousGesture(_:isEnabled:)**：将手势附加到视图，以便与视图定义的其他手势同时处理。

- **simultaneousGesture(_:name:isEnabled:)**：将手势附加到视图，以便与视图定义的其他手势同时处理。

- **SequenceGesture**：由两个手势组成的序列手势。

- **SimultaneousGesture**：包含两个手势的组合手势，这两个手势可以同时执行，互不先后。

- **ExclusiveGesture**：包含两个手势的组合手势，其中只有一个手势会成功执行。

## 定义自定义手势

- **highPriorityGesture(_:including:)**：将一个手势附加到视图，其优先级高于视图中已定义的手势。

- **highPriorityGesture(_:isEnabled:)**：将一个手势附加到视图，其优先级高于视图中已定义的手势。

- **highPriorityGesture(_:name:isEnabled:)**：将一个手势附加到视图，其优先级高于视图中已定义的手势。

- **handGestureShortcut(_:isEnabled:)**：为修改后的控件分配一个手势快捷键。

- **defersSystemGestures(on:)**：设置屏幕边缘，在此边缘，您的手势将优先于系统手势。

- **Gesture**：一个将事件序列与手势匹配的实例，并返回其每个状态的值流。

- **AnyGesture**：一个擦除输入的手势。

- **HandActivationBehavior**：一种专门用于手部输入的激活行为。

- **HandGestureShortcut**：手势快捷方式描述了用户可以通过手指和手腕的动作来激活按钮或切换开关。

## 管理手势状态

- **GestureState**：一种属性包装器类型，在用户执行手势时更新属性，并在手势结束时将属性重置为其初始状态。

- **GestureStateGesture**：用于更新手势更新回调函数所提供状态的手势。

## 处理激活事件

- **allowsWindowActivationEvents(_:)**：配置此视图层级结构中的手势是否可以处理激活包含窗口的事件。

## 已弃用的手势

- **MagnificationGesture**：用于识别放大动作并跟踪放大倍数的手势。

- **RotationGesture**：用于识别旋转动作并跟踪旋转角度的手势。

## 事件处理

- **输入事件**：响应来自硬件设备（例如键盘或触控栏）的输入。

- **Clipboard**：允许用户通过发出复制和粘贴命令来移动或复制项目。

- **拖放**：允许用户通过拖动将项目从一个位置移动到另一个位置，从而实现项目移动或复制。

- **Focus**：识别并控制哪些可见对象响应用户交互。

- **系统事件**：响应系统事件，例如打开 URL。


---
source: https://developer.apple.com/documentation/SwiftUI/Gestures
crawled: 2025-12-02T17:42:32Z
---

# Gestures

**API Collection**

Define interactions from taps, clicks, and swipes to fine-grained gestures.

## Overview

Respond to gestures by adding gesture modifiers to your views. You can listen for taps, drags, pinches, and other standard gestures.



You can also compose custom gestures from individual gestures using the [simultaneously(with:)](Gesture/simultaneously_with.zh-Hans.md), [sequenced(before:)](Gesture/sequenced_before.zh-Hans.md), or [exclusively(before:)](Gesture/exclusively_before.zh-Hans.md) modifiers, or combine gestures with keyboard modifiers using the [modifiers(_:)](Gesture/modifiers.zh-Hans.md) modifier.



For design guidance, see [doc://com.apple.documentation/design/Human-Interface-Guidelines/gestures] in the Human Interface Guidelines.

## Essentials

- **Adding interactivity with gestures**: Use gesture modifiers to add interactivity to your app.

## Recognizing tap gestures

- **onTapGesture(count:perform:)**: Adds an action to perform when this view recognizes a tap gesture.
- **onTapGesture(count:coordinateSpace:perform:)**: Adds an action to perform when this view recognizes a tap gesture, and provides the action with the location of the interaction.
- **TapGesture**: A gesture that recognizes one or more taps.
- **SpatialTapGesture**: A gesture that recognizes one or more taps and reports their location.

## Recognizing long press gestures

- **onLongPressGesture(minimumDuration:maximumDistance:perform:onPressingChanged:)**: Adds an action to perform when this view recognizes a long press gesture.
- **onLongPressGesture(minimumDuration:perform:onPressingChanged:)**: Adds an action to perform when this view recognizes a long press gesture.
- **onLongTouchGesture(minimumDuration:perform:onTouchingChanged:)**: Adds an action to perform when this view recognizes a remote long touch gesture. A long touch gesture is when the finger is on the remote touch surface without actually pressing.
- **LongPressGesture**: A gesture that succeeds when the user performs a long press.

## Recognizing spatial events

- **SpatialEventGesture**: A gesture that provides information about ongoing spatial events like clicks and touches.
- **SpatialEventCollection**: A collection of spatial input events that target a specific view.
- **Chirality**: The chirality, or handedness, of a pose.

## Recognizing gestures that change over time

- **gesture(_:)**: Attaches an [NSGestureRecognizerRepresentable](NSGestureRecognizerRepresentable.zh-Hans.md) to the view.
- **gesture(_:isEnabled:)**: Attaches a gesture to the view with a lower precedence than gestures defined by the view.
- **gesture(_:name:isEnabled:)**: Attaches a gesture to the view with a lower precedence than gestures defined by the view.
- **gesture(_:including:)**: Attaches a gesture to the view with a lower precedence than gestures defined by the view.
- **DragGesture**: A dragging motion that invokes an action as the drag-event sequence changes.
- **WindowDragGesture**: A gesture that recognizes the motion of and handles dragging a window.
- **MagnifyGesture**: A gesture that recognizes a magnification motion and tracks the amount of magnification.
- **RotateGesture**: A gesture that recognizes a rotation motion and tracks the angle of the rotation.
- **RotateGesture3D**: A gesture that recognizes 3D rotation motion and tracks the angle and axis of the rotation.
- **GestureMask**: Options that control how adding a gesture to a view affects other gestures recognized by the view and its subviews.

## Recognizing Apple Pencil gestures

- **onPencilDoubleTap(perform:)**: Adds an action to perform after the user double-taps their Apple Pencil.
- **onPencilSqueeze(perform:)**: Adds an action to perform when the user squeezes their Apple Pencil.
- **preferredPencilDoubleTapAction**: The action that the user prefers to perform after double-tapping their Apple Pencil, as selected in the Settings app.
- **preferredPencilSqueezeAction**: The action that the user prefers to perform when squeezing their Apple Pencil, as selected in the Settings app.
- **PencilPreferredAction**: An action that the user prefers to perform after double-tapping their Apple Pencil.
- **PencilDoubleTapGestureValue**: Describes the value of an Apple Pencil double-tap gesture.
- **PencilSqueezeGestureValue**: Describes the value of an Apple Pencil squeeze gesture.
- **PencilSqueezeGesturePhase**: Describes the phase and value of an Apple Pencil squeeze gesture.
- **PencilHoverPose**: A value describing the location and distance of an Apple Pencil hovering in the area above a view’s bounds.

## Combining gestures

- **Composing SwiftUI gestures**: Combine gestures to create complex interactions.
- **simultaneousGesture(_:including:)**: Attaches a gesture to the view to process simultaneously with gestures defined by the view.
- **simultaneousGesture(_:isEnabled:)**: Attaches a gesture to the view to process simultaneously with gestures defined by the view.
- **simultaneousGesture(_:name:isEnabled:)**: Attaches a gesture to the view to process simultaneously with gestures defined by the view.
- **SequenceGesture**: A gesture that’s a sequence of two gestures.
- **SimultaneousGesture**: A gesture containing two gestures that can happen at the same time with neither of them preceding the other.
- **ExclusiveGesture**: A gesture that consists of two gestures where only one of them can succeed.

## Defining custom gestures

- **highPriorityGesture(_:including:)**: Attaches a gesture to the view with a higher precedence than gestures defined by the view.
- **highPriorityGesture(_:isEnabled:)**: Attaches a gesture to the view with a higher precedence than gestures defined by the view.
- **highPriorityGesture(_:name:isEnabled:)**: Attaches a gesture to the view with a higher precedence than gestures defined by the view.
- **handGestureShortcut(_:isEnabled:)**: Assigns a hand gesture shortcut to the modified control.
- **defersSystemGestures(on:)**: Sets the screen edge from which you want your gesture to take precedence over the system gesture.
- **Gesture**: An instance that matches a sequence of events to a gesture, and returns a stream of values for each of its states.
- **AnyGesture**: A type-erased gesture.
- **HandActivationBehavior**: An activation behavior specific to hand-driven input.
- **HandGestureShortcut**: Hand gesture shortcuts describe finger and wrist movements that the user can perform in order to activate a button or toggle.

## Managing gesture state

- **GestureState**: A property wrapper type that updates a property while the user performs a gesture and resets the property back to its initial state when the gesture ends.
- **GestureStateGesture**: A gesture that updates the state provided by a gesture’s updating callback.

## Handling activation events

- **allowsWindowActivationEvents(_:)**: Configures whether gestures in this view hierarchy can handle events that activate the containing window.

## Deprecated gestures

- **MagnificationGesture**: A gesture that recognizes a magnification motion and tracks the amount of magnification.
- **RotationGesture**: A gesture that recognizes a rotation motion and tracks the angle of the rotation.

## Event handling

- **Input events**: Respond to input from a hardware device, like a keyboard or a Touch Bar.
- **Clipboard**: Enable people to move or duplicate items by issuing Copy and Paste commands.
- **Drag and drop**: Enable people to move or duplicate items by dragging them from one location to another.
- **Focus**: Identify and control which visible object responds to user interaction.
- **System events**: React to system events, like opening a URL.

