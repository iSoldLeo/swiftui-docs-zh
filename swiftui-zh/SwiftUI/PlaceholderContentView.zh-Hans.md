--- 来源：https://developer.apple.com/documentation/SwiftUI/PlaceholderContentView

抓取时间：2025-12-02T17:27:37Z

---

# PlaceholderContentView

**Structure**

用于构建内联修饰符、过渡或其他辅助类型的占位符。

## 声明

```swift
struct PlaceholderContentView<Value>
```

## 概述

您不能直接使用此类型。SwiftUI 会代表您创建此类型。

## 定义过渡

- **transition(_:)**：将过渡与视图关联。

- **Transition**：描述视图添加到视图层次结构或从中移除时要应用的视图更改。

- **TransitionProperties**：`Transition` 可以拥有的属性。

- **TransitionPhase**：指示过渡的当前阶段。

- **AsymmetricTransition**：复合 `Transition`，插入和删除使用不同的过渡效果。

- **AnyTransition**：类型擦除过渡。

- **contentTransition(_:)**：修改视图，使其使用指定的过渡效果作为视图内容更改的动画方法。

- **contentTransition**：视图内容的当前动画方法。

- **contentTransitionAddsDrawingGroup**：一个布尔值，用于控制渲染内容过渡的视图是否使用 GPU 加速渲染。

- **ContentTransition**：一种应用于单个视图内内容的过渡效果，而非视图的插入或移除。

- **navigationTransition(_:)**：设置此视图的导航过渡样式。

- **NavigationTransition**：定义导航到视图时使用的过渡效果的类型。

- **matchedTransitionSource(id:in:)**：将此视图标识为导航过渡（例如缩放过渡）的源。

- **matchedTransitionSource(id:in:configuration:)**：将此视图标识为导航过渡（例如缩放过渡）的源。

- **MatchedTransitionSourceConfiguration**：定义匹配的过渡源外观的配置。

## 符合

- 视图


---
source: https://developer.apple.com/documentation/SwiftUI/PlaceholderContentView
crawled: 2025-12-02T17:27:37Z
---

# PlaceholderContentView

**Structure**

A placeholder used to construct an inline modifier, transition, or other helper type.

## Declaration

```swift
struct PlaceholderContentView<Value>
```

## Overview

You don’t use this type directly. Instead SwiftUI creates this type on your behalf.

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
- **navigationTransition(_:)**: Sets the navigation transition style for this view.
- **NavigationTransition**: A type that defines the transition to use when navigating to a view.
- **matchedTransitionSource(id:in:)**: Identifies this view as the source of a navigation transition, such as a zoom transition.
- **matchedTransitionSource(id:in:configuration:)**: Identifies this view as the source of a navigation transition, such as a zoom transition.
- **MatchedTransitionSourceConfiguration**: A configuration that defines the appearance of a matched transition source.

## Conforms To

- View

