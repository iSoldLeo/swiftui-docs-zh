--- 来源：https://developer.apple.com/documentation/swiftui/transitionproperties
抓取时间：2025-12-04T13:16:50Z

---

# TransitionProperties

**Structure**

过渡效果可以拥有的属性。

## 声明

```swift
struct TransitionProperties
```

## 概述

过渡效果可以拥有指定其高级信息的属性。这可以决定过渡效果如何与其他功能（例如辅助功能设置）交互。

- 另请参阅：`Transition`

## 创建过渡效果属性

- **init(hasMotion:)**

- **hasMotion**：过渡效果是否包含动态效果。

## 定义过渡效果

- **transition(_:)**：将过渡效果与视图关联。

- **Transition**：描述视图添加到视图层次结构或从中移除时要应用的视图更改。

- **TransitionPhase**：指示过渡效果的当前阶段。

- **AsymmetricTransition**：复合过渡效果 `Transition`，插入和移除操作使用不同的过渡效果。

- **AnyTransition**：类型擦除过渡效果。

- **contentTransition(_:)**：修改视图，使其使用给定的过渡效果作为视图内容更改的动画方法。

- **contentTransition**：视图内容的当前动画方法。

- **contentTransitionAddsDrawingGroup**：一个布尔值，用于控制渲染内容过渡的视图是否使用 GPU 加速渲染。

- **ContentTransition**：一种过渡类型，应用于单个视图内的内容，而不是视图的插入或移除。

- **PlaceholderContentView**：用于构造内联修饰符、过渡或其他辅助类型的占位符。

- **navigationTransition(_:)**：设置此视图的导航过渡样式。

- **NavigationTransition**：定义导航到视图时要使用的过渡类型。

- **matchedTransitionSource(id:in:)**：将此视图标识为导航过渡（例如缩放过渡）的源。

- **matchedTransitionSource(id:in:configuration:)**：将此视图标识为导航过渡（例如缩放过渡）的源。

- **MatchedTransitionSourceConfiguration**：定义匹配的过渡源外观的配置。

## 符合以下标准

- Sendable

- SendableMetatype


---
source: https://developer.apple.com/documentation/swiftui/transitionproperties
crawled: 2025-12-04T13:16:50Z
---

# TransitionProperties

**Structure**

The properties a `Transition` can have.

## Declaration

```swift
struct TransitionProperties
```

## Overview

A transition can have properties that specify high level information about it. This can determine how a transition interacts with other features like Accessibility settings.

- See Also: `Transition`

## Creating the transition properties

- **init(hasMotion:)**
- **hasMotion**: Whether the transition includes motion.

## Defining transitions

- **transition(_:)**: Associates a transition with the view.
- **Transition**: A description of view changes to apply when a view is added to and removed from the view hierarchy.
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

## Conforms To

- Sendable
- SendableMetatype

