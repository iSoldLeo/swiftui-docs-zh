---
来源： https://developer.apple.com/documentation/SwiftUI/Focus
抓取时间： 2025-12-02T17:41:26Z
---

# 关注

** 应用程序集**

识别并控制哪个可见对象响应用户交互。

## 概览

焦点表示显示屏中哪个元素接收下一个输入。使用视图修饰符可指示哪些视图可接收焦点、检测哪个视图有焦点，并以编程方式控制焦点状态。



有关设计指导，请参阅《人机界面指南》中的 [doc://com.apple.documentation/design/Human-Interface-Guidelines/focus-and-selection]。

## 要点

- **Focus Cookbook：在您的 SwiftUI 应用程序中支持和增强焦点驱动的交互**：使用可加速键盘输入和支持移动的按键处理程序创建自定义可对焦视图，并以编程方式控制焦点。

## 表示视图可以接收焦点

- **focusable(_:)**：指定视图是否可聚焦。
- **focusable(_:interactions:)**：指定视图是否可聚焦，如果是，它支持哪些聚焦驱动的交互。
- **FocusInteractions**：值描述了视图可支持的不同聚焦交互。

## 管理焦点状态

- **focused(_:equals:)**：通过将视图的焦点状态绑定到给定的状态值来修改该视图。
- **focused(_:)**：通过将焦点状态绑定到给定的布尔状态值来修改此视图。
- **isFocused**：返回最近的可聚焦祖先是否已聚焦。
- **FocusState**：一种属性包装器类型，可以读写一个值，当场景中焦点的位置发生变化时，SwiftUI 会更新该值。
- **FocusedValue**：一个属性包装器，用于观察焦点视图或其某个祖先视图中的值。
- **Entry()**：创建环境值、事务、容器值或焦点值条目。
- **FocusedValueKey**：用于发布和观察重点值时的标识符类型协议。
- **FocusedBinding**：方便的属性包装器，用于观察和自动解除来自聚焦视图或其祖先之一的状态绑定。
- **searchFocused(_:)**：通过将与最近的可搜索修改器相关联的搜索字段的焦点状态绑定到给定的布尔值来修改此视图。
- **searchFocused(_:equals:)**：通过将与最近的可搜索修饰符相关联的搜索字段的焦点状态绑定到给定值来修改此视图。

### 向聚焦视图公开值类型

- **focusedValue(_:)**：设置给定对象类型的聚焦值。
- **focusedValue(_:_:)**：通过注入一个值来修改该视图，该值由您提供给状态依赖于聚焦视图层次结构的其他视图使用。
- **focusedSceneValue(_:)**：在全场景范围内设置给定对象类型的焦点值。
- **focusedSceneValue(_:_:)**：通过注入一个值来修改此视图，该值由您提供给状态依赖于聚焦场景的其他视图使用。
- **FocusedValues**：被聚焦的场景或视图及其祖先导出的状态集合。

## 向聚焦视图公开引用类型

- **focusedObject(_:)**：创建一个新视图，将提供的对象暴露给其他视图，这些视图的状态取决于聚焦视图层次结构。
- **focusedSceneObject(_:)**：创建新视图，将提供的对象显示给其他视图，这些视图的状态取决于活动场景。
- **FocusedObject**：由聚焦视图或其某个祖先提供的可观察对象的属性包装器类型。

## 设置焦点范围

- **focusScope(_:)**：创建一个焦点范围，SwiftUI 使用它来限制默认焦点首选项。
- **focusSection()**：表示应使用视图的框架和可聚焦后代的队列来引导焦点移动。

## 控制默认焦点

- **prefersDefaultFocus(_:in:)**：表示视图在给定命名空间中应默认接收焦点。
- **defaultFocus(_:_:priority:)**：通过为给定的焦点状态绑定赋值来定义窗口中评估默认焦点的区域。
- **DefaultFocusEvaluationPriority**：在不同情况下评估向何处移动焦点时，默认焦点首选项的优先级。

## 重置焦点

- **resetFocus**：请求焦点系统重新评估默认焦点的操作。
- **ResetFocusAction**：提供重新评估默认焦点功能的环境值。

## 配置效果

- **focusEffectDisabled(_:)**：添加控制此视图是否能显示焦点特效（如默认焦点环或悬停特效）的条件。
- **isFocusEffectEnabled**：布尔值，用于指示与此环境关联的视图是否允许显示焦点特效。

## 事件处理

- **Gestures**：定义从点击、单击、轻扫到细粒度手势的交互。
- **输入事件**：响应来自硬件设备（如键盘或触摸条）的输入。
- **Clipboard**：通过发出复制和粘贴命令，使人们能够移动或复制项目。
- **拖放**：通过将项目从一个位置拖到另一个位置，使人们能够移动或复制项目。
- 系统事件**：对系统事件做出反应，如打开 URL。


---
source: https://developer.apple.com/documentation/SwiftUI/Focus
crawled: 2025-12-02T17:41:26Z
---

# Focus

**API Collection**

Identify and control which visible object responds to user interaction.

## Overview

Focus indicates which element in the display receives the next input. Use view modifiers to indicate which views can receive focus, to detect which view has focus, and to programmatically control focus state.



For design guidance, see [doc://com.apple.documentation/design/Human-Interface-Guidelines/focus-and-selection] in the Human Interface Guidelines.

## Essentials

- **Focus Cookbook: Supporting and enhancing focus-driven interactions in your SwiftUI app**: Create custom focusable views with key-press handlers that accelerate keyboard input and support movement, and control focus programmatically.

## Indicating that a view can receive focus

- **focusable(_:)**: Specifies if the view is focusable.
- **focusable(_:interactions:)**: Specifies if the view is focusable, and if so, what focus-driven interactions it supports.
- **FocusInteractions**: Values describe different focus interactions that a view can support.

## Managing focus state

- **focused(_:equals:)**: Modifies this view by binding its focus state to the given state value.
- **focused(_:)**: Modifies this view by binding its focus state to the given Boolean state value.
- **isFocused**: Returns whether the nearest focusable ancestor has focus.
- **FocusState**: A property wrapper type that can read and write a value that SwiftUI updates as the placement of focus within the scene changes.
- **FocusedValue**: A property wrapper for observing values from the focused view or one of its ancestors.
- **Entry()**: Creates an environment values, transaction, container values, or focused values entry.
- **FocusedValueKey**: A protocol for identifier types used when publishing and observing focused values.
- **FocusedBinding**: A convenience property wrapper for observing and automatically unwrapping state bindings from the focused view or one of its ancestors.
- **searchFocused(_:)**: Modifies this view by binding the focus state of the search field associated with the nearest searchable modifier to the given Boolean value.
- **searchFocused(_:equals:)**: Modifies this view by binding the focus state of the search field associated with the nearest searchable modifier to the given value.

## Exposing value types to focused views

- **focusedValue(_:)**: Sets the focused value for the given object type.
- **focusedValue(_:_:)**: Modifies this view by injecting a value that you provide for use by other views whose state depends on the focused view hierarchy.
- **focusedSceneValue(_:)**: Sets the focused value for the given object type at a scene-wide scope.
- **focusedSceneValue(_:_:)**: Modifies this view by injecting a value that you provide for use by other views whose state depends on the focused scene.
- **FocusedValues**: A collection of state exported by the focused scene or view and its ancestors.

## Exposing reference types to focused views

- **focusedObject(_:)**: Creates a new view that exposes the provided object to other views whose whose state depends on the focused view hierarchy.
- **focusedSceneObject(_:)**: Creates a new view that exposes the provided object to other views whose whose state depends on the active scene.
- **FocusedObject**: A property wrapper type for an observable object supplied by the focused view or one of its ancestors.

## Setting focus scope

- **focusScope(_:)**: Creates a focus scope that SwiftUI uses to limit default focus preferences.
- **focusSection()**: Indicates that the view’s frame and cohort of focusable descendants should be used to guide focus movement.

## Controlling default focus

- **prefersDefaultFocus(_:in:)**: Indicates that the view should receive focus by default for a given namespace.
- **defaultFocus(_:_:priority:)**: Defines a region of the window in which default focus is evaluated by assigning a value to a given focus state binding.
- **DefaultFocusEvaluationPriority**: Prioritizations for default focus preferences when evaluating where to move focus in different circumstances.

## Resetting focus

- **resetFocus**: An action that requests the focus system to reevaluate default focus.
- **ResetFocusAction**: An environment value that provides the ability to reevaluate default focus.

## Configuring effects

- **focusEffectDisabled(_:)**: Adds a condition that controls whether this view can display focus effects, such as a default focus ring or hover effect.
- **isFocusEffectEnabled**: A Boolean value that indicates whether the view associated with this environment allows focus effects to be displayed.

## Event handling

- **Gestures**: Define interactions from taps, clicks, and swipes to fine-grained gestures.
- **Input events**: Respond to input from a hardware device, like a keyboard or a Touch Bar.
- **Clipboard**: Enable people to move or duplicate items by issuing Copy and Paste commands.
- **Drag and drop**: Enable people to move or duplicate items by dragging them from one location to another.
- **System events**: React to system events, like opening a URL.

