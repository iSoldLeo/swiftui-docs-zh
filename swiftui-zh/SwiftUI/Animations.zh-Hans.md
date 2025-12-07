--- 来源：https://developer.apple.com/documentation/SwiftUI/Animations
抓取时间：2025-12-02T16:02:48Z

---

# 动画

**API 集合**

响应状态变化，实现流畅的视觉更新。

## 概述

您需要告诉 SwiftUI 如何绘制应用在不同状态下的用户界面，然后依靠 SwiftUI 在状态变化时更新界面。

为了避免状态变化时出现突兀的视觉过渡，可以通过以下方式之一添加动画：

- 通过在调用全局函数 [withAnimation(_:_:)](withAnimation.zh-Hans.md) 中更改状态，为状态变化的所有视觉变化添加动画。

- 通过将 [animation(_:value:)](View/animation___value.zh-Hans.md) 视图修饰符应用于视图，在特定值更改时为特定视图添加动画。

- 使用绑定的 [animation(_:)](Binding/animation.zh-Hans.md) 方法为 [Binding](Binding.zh-Hans.md) 的更改添加动画效果。

SwiftUI 会为许多内置视图修饰符产生的效果添加动画效果，例如设置缩放或不透明度值的修饰符。您可以通过使自定义视图遵循 [Animatable](Animatable.zh-Hans.md) 协议，并告知 SwiftUI 您想要添加动画效果的值，来为其他值添加动画效果。

当动画状态更改导致视图层级结构中添加或移除视图时，您可以使用 [AnyTransition](AnyTransition.zh-Hans.md) 定义的内置过渡效果（例如 [slide](AnyTransition/slide.zh-Hans.md) 或 [scale](AnyTransition/scale.zh-Hans.md)）来告知 SwiftUI 如何过渡视图。您还可以创建自定义过渡效果。

有关设计指南，请参阅《人机界面指南》中的 [doc://com.apple.documentation/design/Human-Interface-Guidelines/motion]。

## 为操作添加基于状态的动画

- **withAnimation(_:_:)**：返回使用提供的动画重新计算视图主体后的结果。

- **withAnimation(_:completionCriteria:_:completion:)**：返回使用提供的动画重新计算视图主体后的结果，并在所有动画完成后运行完成事件。

- **AnimationCompletionCriteria**：确定动画何时完成的条件。

- **Animation**：视图随时间变化的方式，以实现从一个状态到另一个状态的平滑视觉过渡。

## 为视图添加基于状态的动画

- **animation(_:)**：当此视图发生变化时，将给定的动画应用于此视图。

- **animation(_:value:)**：当指定的值发生变化时，将给定的动画应用于此视图。

- **animation(_:body:)**：将给定的动画应用于 `body` 闭包内的所有可动画值。

## 创建基于阶段的动画

- **控制动画的时序和运动**：构建复杂的动画，并使用阶段和关键帧动画器进行控制。

- **phaseAnimator(_:content:animation:)**：为应用于视图的效果添加动画，这些效果会随着一系列连续变化的阶段而变化。

- **phaseAnimator(_:trigger:content:animation:)**：为应用于视图的效果添加动画，这些效果会根据触发器变化，并随着一系列阶段而变化。

- **PhaseAnimator**：一个容器，它通过自动循环播放您提供的一系列阶段来为其内容添加动画，每个阶段定义动画中的一个离散步骤。

## 创建基于关键帧的动画

- **keyframeAnimator(initialValue:repeating:content:keyframes:)**：循环播放指定的关键帧，并使用您在 `body` 中应用的修改器更新视图。

- **keyframeAnimator(initialValue:trigger:content:keyframes:)**：当指定的触发值发生变化时播放指定的关键帧，并使用您在 `body` 中应用的修改器更新视图。

- **KeyframeAnimator**：使用关键帧为其内容添加动画的容器。

- **Keyframes**：定义值随时间变化的类型。

- **KeyframeTimeline**：使用关键帧建模，描述值如何随时间变化的描述。

- **KeyframeTrack**：为根类型的单个属性添加动画的关键帧序列。

- **KeyframeTrackContentBuilder**：构建器，用于根据您在闭包中定义的关键帧创建关键帧轨道内容。

- **KeyframesBuilder**：构建器，用于将关键帧内容值合并为单个值。

- **KeyframeTrackContent**：一组关键帧，用于定义可动画值的插值曲线。

- **CubicKeyframe**：使用三次曲线在值之间平滑插值的关键帧。

- **LinearKeyframe**：使用简单线性插值的关键帧。

- **MoveKeyframe**：直接移动到给定值而不进行插值的关键帧。

- **SpringKeyframe**：使用弹簧函数插值到给定值的关键帧。

## 创建自定义动画

- **CustomAnimation**：定义可动画值随时间变化方式的类型。

- **AnimationContext**：自定义动画可用于管理状态和访问视图环境的上下文值。

- **AnimationState**：存储自定义动画状态的容器。

- **AnimationStateKey**：用于访问动画状态值的键。

- **UnitCurve**：由二维曲线定义的函数，该曲线将 [0,1] 范围内的输入进度映射到同样在 [0,1] 范围内的输出进度。通过改变曲线的形状，可以改变动画或其他插值的有效速度。

- **Spring**：弹簧运动的表示。

## 使数据可动画化

- **Animatable**：描述如何为视图的属性添加动画的类型。

- **AnimatableValues**

- **AnimatablePair**：一对可动画化的值，它们本身也是可动画化的。

- **VectorArithmetic**：可以作为可动画化类型的可动画化数据的类型。

- **EmptyAnimatableData**：用于可动画化数据的空类型。

## 按计划更新视图

- **使用时间线更新 watchOS 应用**：即使用户界面处于非活动状态，也能无缝地安排更新。

- **TimelineView**：根据您提供的计划更新的视图。

- **TimelineSchedule**：提供日期序列的类型，可用作日程安排。

- **TimelineViewDefaultContext**：传递给时间线视图内容回调的信息。

## 同步几何体

- **matchedGeometryEffect(id:in:properties:anchor:isSource:)**：使用您提供的标识符和命名空间定义一组具有同步几何体的视图。

- **MatchedGeometryProperties**：一组视图属性，可以使用 `View.matchedGeometryEffect()` 函数在视图之间同步这些属性。

- **GeometryEffect**：一种效果，可改变视图的视觉外观，但基本不会改变其祖先或后代。

- **Namespace**：一种动态属性类型，允许访问由包含该属性的对象（例如视图）的持久标识定义的命名空间。

- **geometryGroup()**：将视图的几何体（例如位置和大小）与其父视图隔离。

## 定义过渡

- **transition(_:)**：将过渡与视图关联。

- **Transition**：描述在视图添加到视图层次结构和从视图层次结构中移除时要应用的视图更改。

- **TransitionProperties**：`Transition` 可以拥有的属性。

- **TransitionPhase**：指示过渡的当前阶段。

- **AsymmetricTransition**：复合 `Transition`，插入和移除操作使用不同的过渡。

- **AnyTransition**：类型擦除过渡。

- **contentTransition(_:)**：修改视图，使其使用指定的过渡效果作为视图内容动画的实现方式。

- **contentTransition**：当前视图内容动画的实现方式。

- **contentTransitionAddsDrawingGroup**：一个布尔值，用于控制渲染内容过渡效果的视图是否使用 GPU 加速渲染。

- **ContentTransition**：一种应用于单个视图内内容的过渡效果，而不是用于视图的插入或移除。

- **PlaceholderContentView**：用于构造内联修饰符、过渡效果或其他辅助类型的占位符。

- **navigationTransition(_:)**：设置此视图的导航过渡样式。

- **NavigationTransition**：定义导航到视图时使用的过渡效果的类型。 - **matchedTransitionSource(id:in:)**：将此视图标识为导航过渡（例如缩放过渡）的源。

- **matchedTransitionSource(id:in:configuration:)**：将此视图标识为导航过渡（例如缩放过渡）的源。

- **MatchedTransitionSourceConfiguration**：定义匹配过渡源外观的配置。

- **EmptyMatchedTransitionSourceConfiguration**：未设置样式的匹配过渡源配置。

## 将动画移动到另一个视图

- **withTransaction(_:_:)**：使用指定的事务执行闭包并返回结果。

- **withTransaction(_:_:_:)**：使用指定的事务键路径和值执行闭包并返回结果。

- **transaction(_:)**：将给定的事务变更函数应用于视图中使用的所有动画。

- **transaction(value:_:)**：将给定的事务变更函数应用于视图中使用的所有动画。

- **transaction(_:body:)**：将给定的事务变更函数应用于 `body` 闭包中使用的所有动画。

- **Transaction**：当前状态处理更新的上下文。

- **Entry()**：创建环境值、事务、容器值或焦点值条目。

- **TransactionKey**：用于访问事务中值的键。

## 已弃用类型

- **AnimatableModifier**：可以创建带有动画效果的另一个修饰符的修饰符。

## 视图

- **视图基础知识**：使用视图层次结构定义应用程序的视觉元素。

- **视图配置**：调整层级结构中视图的各项属性。

- **视图样式**：为不同类型的视图应用内置和自定义外观及行为。

- **文本输入输出**：显示格式化文本并接收用户输入的文本。

- **Images**：向应用程序的用户界面添加图像和符号。

- **控件和指示器**：显示数值并获取用户选择。

- **菜单和命令**：提供节省空间且上下文相关的命令和控件访问方式。

- **Shapes**：使用颜色、渐变或其他图案描绘和填充内置和自定义形状。

- **绘图和图形**：使用图形效果和自定义绘图增强视图。


---
source: https://developer.apple.com/documentation/SwiftUI/Animations
crawled: 2025-12-02T16:02:48Z
---

# Animations

**API Collection**

Create smooth visual updates in response to state changes.

## Overview

You tell SwiftUI how to draw your app’s user interface for different states, and then rely on SwiftUI to make interface updates when the state changes.



To avoid abrupt visual transitions when the state changes, add animation in one of the following ways:

- Animate all of the visual changes for a state change by changing the state inside a call to the [withAnimation(_:_:)](withAnimation.zh-Hans.md) global function.
- Add animation to a particular view when a specific value changes by applying the [animation(_:value:)](View/animation___value.zh-Hans.md) view modifier to the view.
- Animate changes to a [Binding](Binding.zh-Hans.md) by using the binding’s [animation(_:)](Binding/animation.zh-Hans.md) method.

SwiftUI animates the effects that many built-in view modifiers produce, like those that set a scale or opacity value. You can animate other values by making your custom views conform to the [Animatable](Animatable.zh-Hans.md) protocol, and telling SwiftUI about the value you want to animate.

When an animated state change results in adding or removing a view to or from the view hierarchy, you can tell SwiftUI how to transition the view into or out of place using built-in transitions that [AnyTransition](AnyTransition.zh-Hans.md) defines, like [slide](AnyTransition/slide.zh-Hans.md) or [scale](AnyTransition/scale.zh-Hans.md). You can also create custom transitions.

For design guidance, see [doc://com.apple.documentation/design/Human-Interface-Guidelines/motion] in the Human Interface Guidelines.

## Adding state-based animation to an action

- **withAnimation(_:_:)**: Returns the result of recomputing the view’s body with the provided animation.
- **withAnimation(_:completionCriteria:_:completion:)**: Returns the result of recomputing the view’s body with the provided animation, and runs the completion when all animations are complete.
- **AnimationCompletionCriteria**: The criteria that determines when an animation is considered finished.
- **Animation**: The way a view changes over time to create a smooth visual transition from one state to another.

## Adding state-based animation to a view

- **animation(_:)**: Applies the given animation to this view when this view changes.
- **animation(_:value:)**: Applies the given animation to this view when the specified value changes.
- **animation(_:body:)**: Applies the given animation to all animatable values within the `body` closure.

## Creating phase-based animation

- **Controlling the timing and movements of your animations**: Build sophisticated animations that you control using phase and keyframe animators.
- **phaseAnimator(_:content:animation:)**: Animates effects that you apply to a view over a sequence of phases that change continuously.
- **phaseAnimator(_:trigger:content:animation:)**: Animates effects that you apply to a view over a sequence of phases that change based on a trigger.
- **PhaseAnimator**: A container that animates its content by automatically cycling through a collection of phases that you provide, each defining a discrete step within an animation.

## Creating keyframe-based animation

- **keyframeAnimator(initialValue:repeating:content:keyframes:)**: Loops the given keyframes continuously, updating the view using the modifiers you apply in `body`.
- **keyframeAnimator(initialValue:trigger:content:keyframes:)**: Plays the given keyframes when the given trigger value changes, updating the view using the modifiers you apply in `body`.
- **KeyframeAnimator**: A container that animates its content with keyframes.
- **Keyframes**: A type that defines changes to a value over time.
- **KeyframeTimeline**: A description of how a value changes over time, modeled using keyframes.
- **KeyframeTrack**: A sequence of keyframes animating a single property of a root type.
- **KeyframeTrackContentBuilder**: The builder that creates keyframe track content from the keyframes that you define within a closure.
- **KeyframesBuilder**: A builder that combines keyframe content values into a single value.
- **KeyframeTrackContent**: A group of keyframes that define an interpolation curve of an animatable value.
- **CubicKeyframe**: A keyframe that uses a cubic curve to smoothly interpolate between values.
- **LinearKeyframe**: A keyframe that uses simple linear interpolation.
- **MoveKeyframe**: A keyframe that immediately moves to the given value without interpolating.
- **SpringKeyframe**: A keyframe that uses a spring function to interpolate to the given value.

## Creating custom animations

- **CustomAnimation**: A type that defines how an animatable value changes over time.
- **AnimationContext**: Contextual values that a custom animation can use to manage state and access a view’s environment.
- **AnimationState**: A container that stores the state for a custom animation.
- **AnimationStateKey**: A key for accessing animation state values.
- **UnitCurve**: A  function defined by a two-dimensional curve that maps an input progress in the range [0,1] to an output progress that is also in the range [0,1]. By changing the shape of the curve, the effective speed of an animation or other interpolation can be changed.
- **Spring**: A representation of a spring’s motion.

## Making data animatable

- **Animatable**: A type that describes how to animate a property of a view.
- **AnimatableValues**
- **AnimatablePair**: A pair of animatable values, which is itself animatable.
- **VectorArithmetic**: A type that can serve as the animatable data of an animatable type.
- **EmptyAnimatableData**: An empty type for animatable data.

## Updating a view on a schedule

- **Updating watchOS apps with timelines**: Seamlessly schedule updates to your user interface, even while it’s inactive.
- **TimelineView**: A view that updates according to a schedule that you provide.
- **TimelineSchedule**: A type that provides a sequence of dates for use as a schedule.
- **TimelineViewDefaultContext**: Information passed to a timeline view’s content callback.

## Synchronizing geometries

- **matchedGeometryEffect(id:in:properties:anchor:isSource:)**: Defines a group of views with synchronized geometry using an identifier and namespace that you provide.
- **MatchedGeometryProperties**: A set of view properties that may be synchronized between views using the `View.matchedGeometryEffect()` function.
- **GeometryEffect**: An effect that changes the visual appearance of a view, largely without changing its ancestors or descendants.
- **Namespace**: A dynamic property type that allows access to a namespace defined by the persistent identity of the object containing the property (e.g. a view).
- **geometryGroup()**: Isolates the geometry (e.g. position and size) of the view from its parent view.

## Defining transitions

- **transition(_:)**: Associates a transition with the view.
- **Transition**: A description of view changes to apply when a view is added to and removed from the view hierarchy.
- **TransitionProperties**: The properties a `Transition` can have.
- **TransitionPhase**: An indication of which the current stage of a transition.
- **AsymmetricTransition**: A composite `Transition` that uses a different transition for insertion versus removal.
- **AnyTransition**: A type-erased transition.
- **contentTransition(_:)**: Modifies the view to use a given transition as its method of animating changes to the contents of its views.
- **contentTransition**: The current method of animating the contents of views.
- **contentTransitionAddsDrawingGroup**: A Boolean value that controls whether views that render content transitions use GPU-accelerated rendering.
- **ContentTransition**: A kind of transition that applies to the content within a single view, rather than to the insertion or removal of a view.
- **PlaceholderContentView**: A placeholder used to construct an inline modifier, transition, or other helper type.
- **navigationTransition(_:)**: Sets the navigation transition style for this view.
- **NavigationTransition**: A type that defines the transition to use when navigating to a view.
- **matchedTransitionSource(id:in:)**: Identifies this view as the source of a navigation transition, such as a zoom transition.
- **matchedTransitionSource(id:in:configuration:)**: Identifies this view as the source of a navigation transition, such as a zoom transition.
- **MatchedTransitionSourceConfiguration**: A configuration that defines the appearance of a matched transition source.
- **EmptyMatchedTransitionSourceConfiguration**: An unstyled matched transition source configuration.

## Moving an animation to another view

- **withTransaction(_:_:)**: Executes a closure with the specified transaction and returns the result.
- **withTransaction(_:_:_:)**: Executes a closure with the specified transaction key path and value and returns the result.
- **transaction(_:)**: Applies the given transaction mutation function to all animations used within the view.
- **transaction(value:_:)**: Applies the given transaction mutation function to all animations used within the view.
- **transaction(_:body:)**: Applies the given transaction mutation function to all animations used within the `body` closure.
- **Transaction**: The context of the current state-processing update.
- **Entry()**: Creates an environment values, transaction, container values, or focused values entry.
- **TransactionKey**: A key for accessing values in a transaction.

## Deprecated types

- **AnimatableModifier**: A modifier that can create another modifier with animation.

## Views

- **View fundamentals**: Define the visual elements of your app using a hierarchy of views.
- **View configuration**: Adjust the characteristics of views in a hierarchy.
- **View styles**: Apply built-in and custom appearances and behaviors to different types of views.
- **Text input and output**: Display formatted text and get text input from the user.
- **Images**: Add images and symbols to your app’s user interface.
- **Controls and indicators**: Display values and get user selections.
- **Menus and commands**: Provide space-efficient, context-dependent access to commands and controls.
- **Shapes**: Trace and fill built-in and custom shapes with a color, gradient, or other pattern.
- **Drawing and graphics**: Enhance your views with graphical effects and customized drawings.

