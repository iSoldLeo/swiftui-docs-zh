--- 来源：https://developer.apple.com/documentation/SwiftUI/View-Input-and-Events
抓取时间：2025-12-02T17:22:16Z

---

# 输入和事件修饰符

**API 集合**

为视图提供响应用户输入和系统事件的操作。

## 概述

使用输入和事件修饰符来配置和提供各种用户输入或系统事件的处理程序。例如，您可以检测和控制焦点、响应视图出现和消失等生命周期事件、管理键盘快捷键等等。

## 交互性

- **disabled(_:)**：添加一个条件，用于控制用户是否可以与此视图交互。

- **interactionActivityTrackingTag(_:)**：设置一个用于跟踪交互性的标签。

## 列表控件

- **swipeActions(edge:allowsFullSwipe:content:)**：为列表中的某一行添加自定义滑动操作。

- **refreshable(action:)**：将此视图标记为可刷新。

- **selectionDisabled(_:)**：添加一个条件，用于控制用户是否可以选择此视图。

## 滚动控件

- **scrollPosition(_:anchor:)**：将一个绑定到滚动位置的控件与此视图内的滚动视图关联起来。

- **scrollPosition(id:anchor:)**：关联一个绑定，用于在此视图内的滚动视图滚动时更新。

- **defaultScrollAnchor(_:)**：关联一个锚点，用于控制默认情况下应呈现滚动视图内容的哪一部分。

- **defaultScrollAnchor(_:for:)**：关联一个锚点，用于控制滚动视图在特定情况下的位置。

- **scrollTargetBehavior(_:)**：设置可沿指定轴滚动的视图的滚动行为。

- **scrollTargetLayout(isEnabled:)**：将最外层布局配置为滚动目标布局。

- **scrollTransition(_:axis:transition:)**：应用指定的过渡效果，当此视图在其包含的滚动视图的可见区域内出现和消失时，在过渡效果的各个阶段之间进行动画处理。

- **scrollTransition(topLeading:bottomTrailing:axis:transition:)**：应用指定的过渡效果，当此视图在其包含的滚动视图的可见区域内出现和消失时，在过渡效果的各个阶段之间进行动画处理。

- **onScrollGeometryChange(for:of:action:)**：添加一个操作，当由滚动几何体创建的值发生更改时执行该操作。

- **onScrollTargetVisibilityChange(idType:threshold:_:)**：添加一个操作，该操作将使用有关哪些视图将被视为可见的信息来调用。

- **onScrollVisibilityChange(threshold:_:)**：添加一个操作，当视图跨越屏幕显示/隐藏阈值时调用。

- **onScrollPhaseChange(_:)**：添加一个操作，当层级结构中第一个滚动视图的滚动阶段发生变化时执行。

## 几何体

- **onGeometryChange(for:of:action:)**：添加一个操作，当由几何体代理创建的值发生变化时执行。

## 点击和手势

- **onTapGesture(count:perform:)**：添加一个操作，当此视图识别到点击手势时执行。

- **onTapGesture(count:coordinateSpace:perform:)**：添加一个操作，当此视图识别到点击手势，并为该操作提供交互位置信息时执行。

- **onLongPressGesture(minimumDuration:maximumDistance:perform:onPressingChanged:)**：添加一个操作，当此视图识别到长按手势时执行。

- **onLongPressGesture(minimumDuration:perform:onPressingChanged:)**：添加一个操作，当此视图识别到长按手势时执行。

- **onLongTouchGesture(minimumDuration:perform:onTouchingChanged:)**：添加一个操作，当此视图识别到远程长触手势时执行。长触手势是指手指放在远程触控表面上但未实际按压。

- **gesture(_:)**：将 [NSGestureRecognizerRepresentable](NSGestureRecognizerRepresentable.zh-Hans.md) 附加到视图。

- **gesture(_:isEnabled:)**：将一个手势附加到视图，其优先级低于视图定义的手势。

- **gesture(_:name:isEnabled:)**：将一个手势附加到视图，其优先级低于视图定义的手势。

- **gesture(_:including:)**：将一个手势附加到视图，其优先级低于视图定义的手势。

- **highPriorityGesture(_:including:)**：将一个手势附加到视图，其优先级高于视图自身定义的手势。

- **highPriorityGesture(_:isEnabled:)**：将一个手势附加到视图，其优先级高于视图自身定义的手势。

- **highPriorityGesture(_:name:isEnabled:)**：将一个手势附加到视图，其优先级高于视图自身定义的手势。

- **simultaneousGesture(_:including:)**：将一个手势附加到视图，使其与视图自身定义的手势同时处理。

- **simultaneousGesture(_:isEnabled:)**：将一个手势附加到视图，使其与视图自身定义的手势同时处理。

- **simultaneousGesture(_:name:isEnabled:)**：将一个手势附加到视图，使其与视图自身定义的手势同时处理。

- **defersSystemGestures(on:)**：设置屏幕边缘，在此边缘，您的手势将优先于系统手势。

- **onPencilDoubleTap(perform:)**：添加用户双击 Apple Pencil 后要执行的操作。

- **onPencilSqueeze(perform:)**：添加用户挤压 Apple Pencil 后要执行的操作。

- **allowsWindowActivationEvents(_:)**：配置此视图层级结构中的手势是否可以处理激活包含窗口的事件。

## 键盘输入

- **onKeyPress(_:action:)**：当用户在视图获得焦点时按下硬件键盘上的某个键，则执行此操作。

- **onKeyPress(phases:action:)**：当用户在视图获得焦点时按下硬件键盘上的任意键，则执行此操作。

- **onKeyPress(_:phases:action:)**：当用户在视图获得焦点时按下硬件键盘上的某个键，则执行此操作。

- **onKeyPress(characters:phases:action:)**：当用户在视图获得焦点时按下硬件键盘上的一个或多个键，则执行此操作。

- **onKeyPress(keys:phases:action:)**：当用户在视图获得焦点时按下硬件键盘上的一个或多个键，则执行此操作。

- **onModifierKeysChanged(mask:initial:_:)**：当用户按下或释放硬件修饰键时，则执行此操作。

## 键盘快捷键

- **keyboardShortcut(_:)**：为修改后的控件分配键盘快捷键。

- **keyboardShortcut(_:modifiers:)**：定义键盘快捷键并将其分配给修改后的控件。

- **keyboardShortcut(_:modifiers:localization:)**：定义一个键盘快捷键并将其分配给修改后的控件。

- **modifierKeyAlternate(_:_:)**：创建一个视图，当用户按下指定组合的修饰键时，该视图将替换为修改后的视图。

## 悬停

- **onHover(perform:)**：添加一个操作，当用户将指针移到视图框架上方或下方时执行。

- **onContinuousHover(coordinateSpace:perform:)**：添加一个操作，当指针进入、移动到视图边界内以及离开视图边界时执行。

- **hoverEffect(_:)**：为该视图应用悬停效果。

- **hoverEffect(_:isEnabled:)**：为该视图应用悬停效果。

- **hoverEffect(_:in:isEnabled:)**：为该视图应用悬停效果，并可选择将其添加到 [HoverEffectGroup](HoverEffectGroup.zh-Hans.md)。

- **hoverEffect(in:isEnabled:body:)**：为该视图应用由给定闭包描述的悬停效果。

- **hoverEffectGroup()**：向子视图上定义的所有效果添加隐式 [HoverEffectGroup](HoverEffectGroup.zh-Hans.md)，以便在悬停于该视图或任何子视图时，添加到子视图的所有效果作为一个组激活。

- **hoverEffectGroup(_:)**：向子视图上定义的所有效果添加 [HoverEffectGroup](HoverEffectGroup.zh-Hans.md)，并在悬停于该视图或任何子视图时激活该组。

- **hoverEffectGroup(id:in:behavior:)**：为所有子视图上定义的效果添加 [HoverEffectGroup](HoverEffectGroup.zh-Hans.md)，并在鼠标悬停于此视图或任何子视图上时激活该组。

- **hoverEffectDisabled(_:)**：添加一个条件，用于控制此视图是否可以显示悬停效果。

- **defaultHoverEffect(_:)**：设置此视图内其他视图使用的默认悬停效果。

- **listRowHoverEffect(_:)**：请求包含此视图的列表行使用提供的悬停效果。

- **listRowHoverEffectDisabled(_:)**：请求禁用包含此视图的列表行的悬停效果。

## 指针

- **pointerVisibility(_:)**：设置指针悬停在视图上时的可见性。

- **pointerStyle(_:)**：设置指针悬停在视图上时显示的指针样式。

## 焦点

- **focused(_:equals:)**：通过将焦点状态绑定到给定的状态值来修改此视图。

- **focused(_:)**：通过将焦点状态绑定到给定的布尔状态值来修改此视图。

- **focusedValue(_:)**：设置给定对象类型的焦点值。

- **focusedValue(_:_:)**：通过注入您提供的值来修改此视图，该值可供其他视图使用，这些视图的状态依赖于当前焦点视图的层次结构。

- **focusedSceneValue(_:)**：在场景范围内设置给定对象类型的焦点值。

- **focusedSceneValue(_:_:)**：通过注入您提供的值来修改此视图，供状态依赖于当前焦点场景的其他视图使用。

- **focusedObject(_:)**：创建一个新视图，将提供的对象公开给状态依赖于当前焦点视图层级的其他视图。

- **focusedSceneObject(_:)**：创建一个新视图，将提供的对象公开给状态依赖于当前活动场景的其他视图。

- **prefersDefaultFocus(_:in:)**：指示该视图应默认接收给定命名空间的焦点。

- **focusScope(_:)**：创建一个焦点范围，SwiftUI 使用该范围来限制默认的焦点偏好。

- **focusSection()**：指示应使用视图的框架和可聚焦子视图组来引导焦点移动。

- **focusable(_:)**：指定视图是否可聚焦。

- **focusable(_:interactions:)**：指定视图是否可聚焦，如果可聚焦，则指定其支持哪些基于焦点的交互方式。

- **focusEffectDisabled(_:)**：添加一个条件，用于控制此视图是否可以显示焦点效果，例如默认焦点环或悬停效果。

- **defaultFocus(_:_:priority:)**：定义窗口中用于评估默认焦点的区域，方法是为给定的焦点状态绑定赋值。

- **searchFocused(_:)**：通过将与最近的可搜索修饰符关联的搜索字段的焦点状态绑定到给定的布尔值来修改此视图。

- **searchFocused(_:equals:)**：通过将与最近的可搜索修饰符关联的搜索字段的焦点状态绑定到给定的值来修改此视图。

## 复制和粘贴

- **copyable(_:)**：指定响应系统“复制”命令而要复制的项目列表。

- **cuttable(for:action:)**：指定响应系统“剪切”命令而将项目移动到剪贴板的操作。

- **pasteDestination(for:action:validator:)**：指定响应系统“粘贴”命令而将已验证的项目添加到视图的操作。

- **onCopyCommand(perform:)**：添加响应系统“复制”命令而要执行的操作。

- **onCutCommand(perform:)**：添加响应系统“剪切”命令而要执行的操作。

- **onPasteCommand(of:perform:)**：添加响应系统“粘贴”命令而要执行的操作。

- **onPasteCommand(of:validator:perform:)**：添加一个操作，用于响应系统的“粘贴”命令，并验证相关项目。

## 拖放

- **onDrag(_:preview:)**：激活此视图作为拖放操作的源。

- **onDrag(_:)**：激活此视图作为拖放操作的源。

- **itemProvider(_:)**：提供一个闭包，用于提供特定数据元素的拖放表示形式。

- **onDrop(of:isTargeted:perform:)**：定义拖放操作的目标位置，该目标位置使用您指定的闭包处理拖放的内容。

- **onDrop(of:delegate:)**：定义拖放操作的目标位置，该目标位置使用您提供的委托控制的行为。

- **dropDestination(for:action:isTargeted:)**：定义拖放操作的目标位置，该位置使用您指定的闭包处理拖放的内容。

- **draggable(_:)**：激活此视图作为拖放操作的源。

- **draggable(_:preview:)**：激活此视图作为拖放操作的源。

- **springLoadingBehavior(_:)**：设置此视图的弹簧加载行为。

## 提交

- **onSubmit(of:_:)**：添加用户向此视图提交值时要执行的操作。

- **submitScope(_:)**：防止源自此视图的提交触发器调用视图层次结构中更高层级的提交修饰符配置的提交操作。

- **submitLabel(_:)**：设置此视图的提交标签。

## 移动

- **onMoveCommand(perform:)**：添加一个响应移动命令的操作，例如用户按下 Mac 键盘上的方向键，或在控制 Apple TV 时轻点 Siri Remote 的边缘。

- **moveDisabled(_:)**：添加一个条件，用于判断视图的层级结构是否可移动。

## 删除

- **onDeleteCommand(perform:)**：添加一个响应系统删除命令的操作，或在视图获得焦点时按下 ⌫（退格键）或 ⌦（向前删除键）。

- **deleteDisabled(_:)**：添加一个条件，用于判断视图的层级结构是否可删除。

## 命令

- **pageCommand(value:in:step:)**：响应 Page Up 或 Page Down 命令，使值在指定范围内逐级移动。

- **onExitCommand(perform:)**：设置一个操作，当视图获得焦点时，收到退出命令后触发该操作。

- **onPlayPauseCommand(perform:)**：添加一个操作，用于响应系统的播放/暂停命令。

- **onCommand(_:perform:)**：添加一个操作，用于响应给定的选择器。

## 数码表冠

- **digitalCrownAccessory(_:)**：指定 Apple Watch 上数码表冠配件视图的可见性。

- **digitalCrownAccessory(content:)**：在 Apple Watch 的数码表冠旁边放置一个配件视图。

- **digitalCrownRotation(_:from:through:sensitivity:isContinuous:isHapticFeedbackEnabled:onChange:onIdle:)**：通过更新指定的绑定来跟踪数码表冠的旋转。

- **digitalCrownRotation(_:onChange:onIdle:)**：通过更新指定的绑定来跟踪数码表冠的旋转。

- **digitalCrownRotation(detent:from:through:by:sensitivity:isContinuous:isHapticFeedbackEnabled:onChange:onIdle:)**：通过更新指定的绑定来跟踪数码表冠的旋转。

- **digitalCrownRotation(_:)**：通过更新指定的绑定来跟踪数码表冠的旋转。

- **digitalCrownRotation(_:from:through:by:sensitivity:isContinuous:isHapticFeedbackEnabled:)**：通过更新指定的绑定来跟踪数码表冠的旋转。

## 沉浸式空间

- **onImmersionChange(initial:_:)**：当应用程序的沉浸状态发生变化时执行操作。

## 音量控制

- **onVolumeViewpointChange(updateStrategy:initial:_:)**：添加一个在音量控制视角发生变化时要执行的操作。

- **supportedVolumeViewpoints(_:)**：指定音量控制中窗口栏和装饰条支持的视角。

## 用户活动

- **userActivity(_:element:_:)**：声明用户活动类型。

- **userActivity(_:isActive:_:)**：声明用户活动类型。

- **onContinueUserActivity(_:perform:)**：注册一个处理程序，用于响应应用接收到的用户活动。

- **handlesExternalEvents(preferring:allowing:)**：指定视图场景在已打开时处理的外部事件。

## 视图生命周期

- **onAppear(perform:)**：添加一个在此视图显示之前执行的操作。

- **onDisappear(perform:)**：添加一个在此视图消失之后执行的操作。

- **onChange(of:initial:_:)**：为此视图添加一个修饰符，当特定值更改时触发一个操作。

- **task(priority:_:)**：添加一个在此视图显示之前执行的异步任务。

- **task(id:priority:_:)**：添加一个任务，在该视图显示之前或指定值更改时执行。

## 文件重命名

- **renameAction(_:)**：设置一个用于重命名操作的闭包。

## URL

- **onOpenURL(perform:)**：注册一个处理程序，以便在应用接收到 URL 时调用。

- **widgetURL(_:)**：设置用户点击小部件时要在包含应用中打开的 URL。

## 发布者事件

- **onReceive(_:perform:)**：添加一个操作，当此视图检测到给定发布者发出的数据时执行。

## 命中测试

- **allowsHitTesting(_:)**：配置此视图是否参与命中测试操作。

## 内容形状

- **contentShape(_:eoFill:)**：定义命中测试的内容形状。

- **contentShape(_:_:eoFill:)**：设置此视图的内容形状。

## 导入和导出

- **exportsItemProviders(_:onExport:)**：导出只读项目提供程序，供快捷指令、快速操作和服务使用。

- **exportsItemProviders(_:onExport:onEdit:)**：导出读写项目提供程序，供快捷指令、快速操作和服务使用。

- **importsItemProviders(_:onImport:)**：启用从服务（例如 macOS 上的“连续互通相机”）导入项目提供程序的功能。

- **exportableToServices(_:)**：导出项目，供快捷指令、快速操作和服务使用。

- **exportableToServices(_:onEdit:)**：导出读写项目，供快捷指令、快速操作和服务使用。

- **importableFromServices(for:action:)**：启用从服务导入项目，例如 macOS 上的“连续互通相机”。

## 应用意图

- **shortcutsLinkStyle(_:)**：设置视图层级结构中“快捷指令链接”的样式。

- **siriTipViewStyle(_:)**：设置视图层级结构中“Siri提示视图”的样式。

## 相机

- **onCameraCaptureEvent(isEnabled:action:)**：用于注册由系统捕获事件触发的操作。

- **onCameraCaptureEvent(isEnabled:primaryAction:secondaryAction:)**：用于注册由系统捕获事件触发的操作。

- **cameraAnchor(isActive:)**：指定用作 Apple Vision Pro 2D Persona 流虚拟相机的视图。

## 提供交互性

- **搜索修饰符**：允许用户在您的应用中搜索内容。

- **呈现修饰符**：定义在特定条件下要呈现的视图的附加视图。

- **状态修饰符**：访问存储并为子视图提供配置数据。


---
source: https://developer.apple.com/documentation/SwiftUI/View-Input-and-Events
crawled: 2025-12-02T17:22:16Z
---

# Input and event modifiers

**API Collection**

Supply actions for a view to perform in response to user input and system events.

## Overview

Use input and event modifiers to configure and provide handlers for a wide variety of user inputs or system events. For example, you can detect and control focus, respond to life cycle events like view appearance and disappearance, manage keyboard shortcuts, and much more.

## Interactivity

- **disabled(_:)**: Adds a condition that controls whether users can interact with this view.
- **interactionActivityTrackingTag(_:)**: Sets a tag that you use for tracking interactivity.

## List controls

- **swipeActions(edge:allowsFullSwipe:content:)**: Adds custom swipe actions to a row in a list.
- **refreshable(action:)**: Marks this view as refreshable.
- **selectionDisabled(_:)**: Adds a condition that controls whether users can select this view.

## Scroll controls

- **scrollPosition(_:anchor:)**: Associates a binding to a scroll position with a scroll view within this view.
- **scrollPosition(id:anchor:)**: Associates a binding to be updated when a scroll view within this view scrolls.
- **defaultScrollAnchor(_:)**: Associates an anchor to control which part of the scroll view’s content should be rendered by default.
- **defaultScrollAnchor(_:for:)**: Associates an anchor to control the position of a scroll view in a particular circumstance.
- **scrollTargetBehavior(_:)**: Sets the scroll behavior of views scrollable in the provided axes.
- **scrollTargetLayout(isEnabled:)**: Configures the outermost layout as a scroll target layout.
- **scrollTransition(_:axis:transition:)**: Applies the given transition, animating between the phases of the transition as this view appears and disappears within the visible region of the containing scroll view.
- **scrollTransition(topLeading:bottomTrailing:axis:transition:)**: Applies the given transition, animating between the phases of the transition as this view appears and disappears within the visible region of the containing scroll view.
- **onScrollGeometryChange(for:of:action:)**: Adds an action to be performed when a value, created from a scroll geometry, changes.
- **onScrollTargetVisibilityChange(idType:threshold:_:)**: Adds an action to be called with information about what views would be considered visible.
- **onScrollVisibilityChange(threshold:_:)**: Adds an action to be called when the view crosses the threshold to be considered on/off screen.
- **onScrollPhaseChange(_:)**: Adds an action to perform when the scroll phase of the first scroll view in the hierarchy changes.

## Geometry

- **onGeometryChange(for:of:action:)**: Adds an action to be performed when a value, created from a geometry proxy, changes.

## Taps and gestures

- **onTapGesture(count:perform:)**: Adds an action to perform when this view recognizes a tap gesture.
- **onTapGesture(count:coordinateSpace:perform:)**: Adds an action to perform when this view recognizes a tap gesture, and provides the action with the location of the interaction.
- **onLongPressGesture(minimumDuration:maximumDistance:perform:onPressingChanged:)**: Adds an action to perform when this view recognizes a long press gesture.
- **onLongPressGesture(minimumDuration:perform:onPressingChanged:)**: Adds an action to perform when this view recognizes a long press gesture.
- **onLongTouchGesture(minimumDuration:perform:onTouchingChanged:)**: Adds an action to perform when this view recognizes a remote long touch gesture. A long touch gesture is when the finger is on the remote touch surface without actually pressing.
- **gesture(_:)**: Attaches an [NSGestureRecognizerRepresentable](NSGestureRecognizerRepresentable.zh-Hans.md) to the view.
- **gesture(_:isEnabled:)**: Attaches a gesture to the view with a lower precedence than gestures defined by the view.
- **gesture(_:name:isEnabled:)**: Attaches a gesture to the view with a lower precedence than gestures defined by the view.
- **gesture(_:including:)**: Attaches a gesture to the view with a lower precedence than gestures defined by the view.
- **highPriorityGesture(_:including:)**: Attaches a gesture to the view with a higher precedence than gestures defined by the view.
- **highPriorityGesture(_:isEnabled:)**: Attaches a gesture to the view with a higher precedence than gestures defined by the view.
- **highPriorityGesture(_:name:isEnabled:)**: Attaches a gesture to the view with a higher precedence than gestures defined by the view.
- **simultaneousGesture(_:including:)**: Attaches a gesture to the view to process simultaneously with gestures defined by the view.
- **simultaneousGesture(_:isEnabled:)**: Attaches a gesture to the view to process simultaneously with gestures defined by the view.
- **simultaneousGesture(_:name:isEnabled:)**: Attaches a gesture to the view to process simultaneously with gestures defined by the view.
- **defersSystemGestures(on:)**: Sets the screen edge from which you want your gesture to take precedence over the system gesture.
- **onPencilDoubleTap(perform:)**: Adds an action to perform after the user double-taps their Apple Pencil.
- **onPencilSqueeze(perform:)**: Adds an action to perform when the user squeezes their Apple Pencil.
- **allowsWindowActivationEvents(_:)**: Configures whether gestures in this view hierarchy can handle events that activate the containing window.

## Keyboard input

- **onKeyPress(_:action:)**: Performs an action if the user presses a key on a hardware keyboard while the view has focus.
- **onKeyPress(phases:action:)**: Performs an action if the user presses any key on a hardware keyboard while the view has focus.
- **onKeyPress(_:phases:action:)**: Performs an action if the user presses a key on a hardware keyboard while the view has focus.
- **onKeyPress(characters:phases:action:)**: Performs an action if the user presses one or more keys on a hardware keyboard while the view has focus.
- **onKeyPress(keys:phases:action:)**: Performs an action if the user presses one or more keys on a hardware keyboard while the view has focus.
- **onModifierKeysChanged(mask:initial:_:)**: Performs an action whenever the user presses or releases a hardware modifier key.

## Keyboard shortcuts

- **keyboardShortcut(_:)**: Assigns a keyboard shortcut to the modified control.
- **keyboardShortcut(_:modifiers:)**: Defines a keyboard shortcut and assigns it to the modified control.
- **keyboardShortcut(_:modifiers:localization:)**: Defines a keyboard shortcut and assigns it to the modified control.
- **modifierKeyAlternate(_:_:)**: Builds a view to use in place of the modified view when the user presses the modifier key(s) indicated by the given set.

## Hover

- **onHover(perform:)**: Adds an action to perform when the user moves the pointer over or away from the view’s frame.
- **onContinuousHover(coordinateSpace:perform:)**: Adds an action to perform when the pointer enters, moves within, and exits the view’s bounds.
- **hoverEffect(_:)**: Applies a hover effect to this view.
- **hoverEffect(_:isEnabled:)**: Applies a hover effect to this view.
- **hoverEffect(_:in:isEnabled:)**: Applies a hover effect to this view, optionally adding it to a [HoverEffectGroup](HoverEffectGroup.zh-Hans.md).
- **hoverEffect(in:isEnabled:body:)**: Applies a hover effect to this view described by the given closure.
- **hoverEffectGroup()**: Adds an implicit [HoverEffectGroup](HoverEffectGroup.zh-Hans.md) to all effects defined on descendant views, so that all effects added to subviews activate as a group whenever this view or any descendant views are hovered.
- **hoverEffectGroup(_:)**: Adds a [HoverEffectGroup](HoverEffectGroup.zh-Hans.md) to all effects defined on descendant views, and activates the group whenever this view or any descendant views are hovered.
- **hoverEffectGroup(id:in:behavior:)**: Adds a [HoverEffectGroup](HoverEffectGroup.zh-Hans.md) to all effects defined on descendant views, and activates the group whenever this view or any descendant views are hovered.
- **hoverEffectDisabled(_:)**: Adds a condition that controls whether this view can display hover effects.
- **defaultHoverEffect(_:)**: Sets the default hover effect to use for views within this view.
- **listRowHoverEffect(_:)**: Requests that the containing list row use the provided hover effect.
- **listRowHoverEffectDisabled(_:)**: Requests that the containing list row have its hover effect disabled.

## Pointer

- **pointerVisibility(_:)**: Sets the visibility of the pointer when it’s over the view.
- **pointerStyle(_:)**: Sets the pointer style to display when the pointer is over the view.

## Focus

- **focused(_:equals:)**: Modifies this view by binding its focus state to the given state value.
- **focused(_:)**: Modifies this view by binding its focus state to the given Boolean state value.
- **focusedValue(_:)**: Sets the focused value for the given object type.
- **focusedValue(_:_:)**: Modifies this view by injecting a value that you provide for use by other views whose state depends on the focused view hierarchy.
- **focusedSceneValue(_:)**: Sets the focused value for the given object type at a scene-wide scope.
- **focusedSceneValue(_:_:)**: Modifies this view by injecting a value that you provide for use by other views whose state depends on the focused scene.
- **focusedObject(_:)**: Creates a new view that exposes the provided object to other views whose whose state depends on the focused view hierarchy.
- **focusedSceneObject(_:)**: Creates a new view that exposes the provided object to other views whose whose state depends on the active scene.
- **prefersDefaultFocus(_:in:)**: Indicates that the view should receive focus by default for a given namespace.
- **focusScope(_:)**: Creates a focus scope that SwiftUI uses to limit default focus preferences.
- **focusSection()**: Indicates that the view’s frame and cohort of focusable descendants should be used to guide focus movement.
- **focusable(_:)**: Specifies if the view is focusable.
- **focusable(_:interactions:)**: Specifies if the view is focusable, and if so, what focus-driven interactions it supports.
- **focusEffectDisabled(_:)**: Adds a condition that controls whether this view can display focus effects, such as a default focus ring or hover effect.
- **defaultFocus(_:_:priority:)**: Defines a region of the window in which default focus is evaluated by assigning a value to a given focus state binding.
- **searchFocused(_:)**: Modifies this view by binding the focus state of the search field associated with the nearest searchable modifier to the given Boolean value.
- **searchFocused(_:equals:)**: Modifies this view by binding the focus state of the search field associated with the nearest searchable modifier to the given value.

## Copy and paste

- **copyable(_:)**: Specifies a list of items to copy in response to the system’s Copy command.
- **cuttable(for:action:)**: Specifies an action that moves items to the Clipboard in response to the system’s Cut command.
- **pasteDestination(for:action:validator:)**: Specifies an action that adds validated items to a view in response to the system’s Paste command.
- **onCopyCommand(perform:)**: Adds an action to perform in response to the system’s Copy command.
- **onCutCommand(perform:)**: Adds an action to perform in response to the system’s Cut command.
- **onPasteCommand(of:perform:)**: Adds an action to perform in response to the system’s Paste command.
- **onPasteCommand(of:validator:perform:)**: Adds an action to perform in response to the system’s Paste command with items that you validate.

## Drag and drop

- **onDrag(_:preview:)**: Activates this view as the source of a drag and drop operation.
- **onDrag(_:)**: Activates this view as the source of a drag and drop operation.
- **itemProvider(_:)**: Provides a closure that vends the drag representation to be used for a particular data element.
- **onDrop(of:isTargeted:perform:)**: Defines the destination of a drag-and-drop operation that handles the dropped content with a closure that you specify.
- **onDrop(of:delegate:)**: Defines the destination of a drag and drop operation using behavior controlled by the delegate that you provide.
- **dropDestination(for:action:isTargeted:)**: Defines the destination of a drag and drop operation that handles the dropped content with a closure that you specify.
- **draggable(_:)**: Activates this view as the source of a drag and drop operation.
- **draggable(_:preview:)**: Activates this view as the source of a drag and drop operation.
- **springLoadingBehavior(_:)**: Sets the spring loading behavior this view.

## Submission

- **onSubmit(of:_:)**: Adds an action to perform when the user submits a value to this view.
- **submitScope(_:)**: Prevents submission triggers originating from this view to invoke a submission action configured by a submission modifier higher up in the view hierarchy.
- **submitLabel(_:)**: Sets the submit label for this view.

## Movement

- **onMoveCommand(perform:)**: Adds an action to perform in response to a move command, like when the user presses an arrow key on a Mac keyboard, or taps the edge of the Siri Remote when controlling an Apple TV.
- **moveDisabled(_:)**: Adds a condition for whether the view’s view hierarchy is movable.

## Deletion

- **onDeleteCommand(perform:)**: Adds an action to perform in response to the system’s Delete command, or pressing either the ⌫ (backspace) or ⌦ (forward delete) keys while the view has focus.
- **deleteDisabled(_:)**: Adds a condition for whether the view’s view hierarchy is deletable.

## Commands

- **pageCommand(value:in:step:)**: Steps a value through a range in response to page up or page down commands.
- **onExitCommand(perform:)**: Sets up an action that triggers in response to receiving the exit command while the view has focus.
- **onPlayPauseCommand(perform:)**: Adds an action to perform in response to the system’s Play/Pause command.
- **onCommand(_:perform:)**: Adds an action to perform in response to the given selector.

## Digital crown

- **digitalCrownAccessory(_:)**: Specifies the visibility of Digital Crown accessory Views on Apple Watch.
- **digitalCrownAccessory(content:)**: Places an accessory View next to the Digital Crown on Apple Watch.
- **digitalCrownRotation(_:from:through:sensitivity:isContinuous:isHapticFeedbackEnabled:onChange:onIdle:)**: Tracks Digital Crown rotations by updating the specified binding.
- **digitalCrownRotation(_:onChange:onIdle:)**: Tracks Digital Crown rotations by updating the specified binding.
- **digitalCrownRotation(detent:from:through:by:sensitivity:isContinuous:isHapticFeedbackEnabled:onChange:onIdle:)**: Tracks Digital Crown rotations by updating the specified binding.
- **digitalCrownRotation(_:)**: Tracks Digital Crown rotations by updating the specified binding.
- **digitalCrownRotation(_:from:through:by:sensitivity:isContinuous:isHapticFeedbackEnabled:)**: Tracks Digital Crown rotations by updating the specified binding.

## Immersive Spaces

- **onImmersionChange(initial:_:)**: Performs an action when the immersion state of your app changes.

## Volumes

- **onVolumeViewpointChange(updateStrategy:initial:_:)**: Adds an action to perform when the viewpoint of the volume changes.
- **supportedVolumeViewpoints(_:)**: Specifies which viewpoints are supported for the window bar and ornaments in a volume.

## User activities

- **userActivity(_:element:_:)**: Advertises a user activity type.
- **userActivity(_:isActive:_:)**: Advertises a user activity type.
- **onContinueUserActivity(_:perform:)**: Registers a handler to invoke in response to a user activity that your app receives.
- **handlesExternalEvents(preferring:allowing:)**: Specifies the external events that the view’s scene handles if the scene is already open.

## View life cycle

- **onAppear(perform:)**: Adds an action to perform before this view appears.
- **onDisappear(perform:)**: Adds an action to perform after this view disappears.
- **onChange(of:initial:_:)**: Adds a modifier for this view that fires an action when a specific value changes.
- **task(priority:_:)**: Adds an asynchronous task to perform before this view appears.
- **task(id:priority:_:)**: Adds a task to perform before this view appears or when a specified value changes.

## File renaming

- **renameAction(_:)**: Sets a closure to run for the rename action.

## URLs

- **onOpenURL(perform:)**: Registers a handler to invoke in response to a URL that your app receives.
- **widgetURL(_:)**: Sets the URL to open in the containing app when the user clicks the widget.

## Publisher events

- **onReceive(_:perform:)**: Adds an action to perform when this view detects data emitted by the given publisher.

## Hit testing

- **allowsHitTesting(_:)**: Configures whether this view participates in hit test operations.

## Content shape

- **contentShape(_:eoFill:)**: Defines the content shape for hit testing.
- **contentShape(_:_:eoFill:)**: Sets the content shape for this view.

## Import and export

- **exportsItemProviders(_:onExport:)**: Exports a read-only item provider for consumption by shortcuts, quick actions, and services.
- **exportsItemProviders(_:onExport:onEdit:)**: Exports a read-write item provider for consumption by shortcuts, quick actions, and services.
- **importsItemProviders(_:onImport:)**: Enables importing item providers from services, such as Continuity Camera on macOS.
- **exportableToServices(_:)**: Exports items for consumption by shortcuts, quick actions, and services.
- **exportableToServices(_:onEdit:)**: Exports read-write items for consumption by shortcuts, quick actions, and services.
- **importableFromServices(for:action:)**: Enables importing items from services, such as Continuity Camera on macOS.

## App intents

- **shortcutsLinkStyle(_:)**: Sets the given style for ShortcutsLinks within the view hierarchy
- **siriTipViewStyle(_:)**: Sets the given style for SiriTipView within the view hierarchy

## Camera

- **onCameraCaptureEvent(isEnabled:action:)**: Used to register an action triggered by system capture events.
- **onCameraCaptureEvent(isEnabled:primaryAction:secondaryAction:)**: Used to register actions triggered by system capture events.
- **cameraAnchor(isActive:)**: Specifies the view that should act as the virtual camera for Apple Vision Pro 2D Persona stream.

## Providing interactivity

- **Search modifiers**: Enable people to search for content in your app.
- **Presentation modifiers**: Define additional views for the view to present under specified conditions.
- **State modifiers**: Access storage and provide child views with configuration data.

