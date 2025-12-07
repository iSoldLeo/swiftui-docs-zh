--- 来源：https://developer.apple.com/documentation/swiftui/anytransition
抓取时间：2025-12-04T13:16:51Z

---

# AnyTransition

**Structure**

类型擦除过渡效果。

## 声明

```swift
@frozen struct AnyTransition
```

## 概述

- 另请参阅：`Transition`

## 获取内置过渡效果

- **identity**：返回输入视图（未修改）作为输出视图的过渡效果。

- **move(edge:)**：返回将视图移向指定边缘的过渡效果。

- **offset(_:)**

- **offset(x:y:)**

- **opacity**：插入时从透明到不透明的过渡效果，移除时从不透明到透明的过渡效果。

- **push(from:)**：创建一个过渡效果，添加到视图后，视图插入时会从指定边缘向内移动并淡入，移除时会从另一边缘向外移动并淡出。

- **scale**：返回一个缩放视图的过渡效果。

- **scale(scale:anchor:)**：返回一个按指定比例缩放视图的过渡效果。

- **slide**：插入时从前缘向内移动，移除时向后缘向外移动。

## 组合和配置过渡效果

- **animation(_:)**：为该过渡效果附加动画。

- **asymmetric(insertion:removal:)**：提供一个复合过渡效果，插入和移除操作使用不同的过渡效果。

- **combined(with:)**：将此过渡效果与另一个过渡效果组合，返回一个应用了两个过渡效果的新过渡效果。

## 创建自定义过渡效果

- **init(_:)**：创建一个实例，该实例会擦除 `transition` 的类型。

- **modifier(active:identity:)**：返回一个在活动修饰符和标识修饰符之间定义的过渡效果。

## 定义过渡效果

- **transition(_:)**：将过渡效果与视图关联。

- **Transition**：视图添加到视图层次结构或从中移除时要应用的视图更改的描述。

- **TransitionProperties**：`Transition` 可以拥有的属性。

- **TransitionPhase**：指示当前转换阶段。

- **AsymmetricTransition**：复合 `Transition`，插入和移除操作使用不同的转换。

- **contentTransition(_:)**：修改视图，使其使用给定的转换作为其内容更改动画的方法。

- **contentTransition**：当前视图内容动画的方法。

- **contentTransitionAddsDrawingGroup**：一个布尔值，用于控制渲染内容过渡的视图是否使用 GPU 加速渲染。

- **ContentTransition**：一种过渡类型，应用于单个视图内的内容，而不是视图的插入或移除。

- **PlaceholderContentView**：用于构造内联修饰符、过渡或其他辅助类型的占位符。

- **navigationTransition(_:)**：设置此视图的导航过渡样式。

- **NavigationTransition**：定义导航到视图时要使用的过渡类型。

- **matchedTransitionSource(id:in:)**：将此视图标识为导航过渡（例如缩放过渡）的源。

- **matchedTransitionSource(id:in:configuration:)**：将此视图标识为导航过渡（例如缩放过渡）的源。

- **MatchedTransitionSourceConfiguration**：定义匹配的过渡源外观的配置。


---
source: https://developer.apple.com/documentation/swiftui/anytransition
crawled: 2025-12-04T13:16:51Z
---

# AnyTransition

**Structure**

A type-erased transition.

## Declaration

```swift
@frozen struct AnyTransition
```

## Overview

- See Also: `Transition`

## Getting built-in transitions

- **identity**: A transition that returns the input view, unmodified, as the output view.
- **move(edge:)**: Returns a transition that moves the view away, towards the specified edge of the view.
- **offset(_:)**
- **offset(x:y:)**
- **opacity**: A transition from transparent to opaque on insertion, and from opaque to transparent on removal.
- **push(from:)**: Creates a transition that when added to a view will animate the view’s insertion by moving it in from the specified edge while fading it in, and animate its removal by moving it out towards the opposite edge and fading it out.
- **scale**: Returns a transition that scales the view.
- **scale(scale:anchor:)**: Returns a transition that scales the view by the specified amount.
- **slide**: A transition that inserts by moving in from the leading edge, and removes by moving out towards the trailing edge.

## Combining and configuring transitions

- **animation(_:)**: Attaches an animation to this transition.
- **asymmetric(insertion:removal:)**: Provides a composite transition that uses a different transition for insertion versus removal.
- **combined(with:)**: Combines this transition with another, returning a new transition that is the result of both transitions being applied.

## Creating a custom transition

- **init(_:)**: Create an instance that type-erases `transition`.
- **modifier(active:identity:)**: Returns a transition defined between an active modifier and an identity modifier.

## Defining transitions

- **transition(_:)**: Associates a transition with the view.
- **Transition**: A description of view changes to apply when a view is added to and removed from the view hierarchy.
- **TransitionProperties**: The properties a `Transition` can have.
- **TransitionPhase**: An indication of which the current stage of a transition.
- **AsymmetricTransition**: A composite `Transition` that uses a different transition for insertion versus removal.
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

