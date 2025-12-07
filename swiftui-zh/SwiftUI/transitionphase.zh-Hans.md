---
来源： https://developer.apple.com/documentation/swiftui/transitionphase
抓取时间： 2025-12-04T13:16:10Z
---

# 过渡阶段

**Enumeration**

表示过渡的当前阶段。

## 声明

```swift
@frozen enum TransitionPhase
```

## 概览

当一个视图出现过渡时，首先显示的是 `willAppear` 阶段，然后会立即移动到 `identity` 阶段。当一个视图被移除时，其过渡会从`identity`阶段变为`didDisappear`阶段。如果一个视图在过渡时被移除，那么它的阶段将变为 `didDisappear`。如果视图在转出时被重新添加，其阶段将变回 `identity`。

在`identity` 阶段，过渡一般不会对所应用的视图做任何视觉上的改变，因为只要视图可见，过渡在`identity` 阶段所做的视图修改就会应用到该视图上。在`willAppear` 和`didDisappear` 阶段，过渡应该应用一个可动画的变化来创建过渡。如果没有应用可动画化的变化，则过渡将是无操作的。

- 另请参阅： `Transition`
- 另请参阅： `AnyTransition`

## 获取相位

- **TransitionPhase.identity**：转换正应用于视图层次结构中的视图。
- **TransitionPhase.willAppear**：转换正应用于即将插入视图层次结构的视图。
- **TransitionPhase.didDisappear**：该转换正应用于已请求从视图层次结构中删除的视图。

## 获取阶段特征

- **isIdentity**：布尔值，表示转换是否具有标识效果，即不改变视图的外观。
- **value**：一个数值，用于乘以根据不同阶段应用的不同效果。

## 定义过渡

- **transition(_:)**：将过渡效果与视图关联。
- **Transition**：当视图添加到视图层次结构或从视图层次结构中移除视图时要应用的视图更改描述。
- **TransitionProperties**：`Transition`可具有的属性。
- **AsymmetricTransition**：复合`Transition`，在插入和移除时使用不同的过渡。
- **AnyTransition**：类型抹除的转换。
- **contentTransition(_:)**：修改视图，使其使用给定的转换作为其视图内容变化的动画方法。
- **contentTransition**：视图内容的当前动画方法。
- **contentTransitionAddsDrawingGroup**：一个布尔值，用于控制渲染内容转换的视图是否使用 GPU 加速渲染。
- **ContentTransition**：一种过渡，适用于单个视图中的内容，而不是视图的插入或移除。
- **PlaceholderContentView**：用于构建内联修饰符、转换或其他辅助类型的占位符。
- **navigationTransition(_:)**：为该视图设置导航过渡样式。
- **NavigationTransition**：定义导航到视图时使用的过渡类型。
- **matchedTransitionSource(id:in:)**：将此视图标识为导航转换（如缩放转换）的源。
- **matchedTransitionSource(id:in:configuration:)**：将此视图标识为导航转换（如缩放转换）的源。
- **MatchedTransitionSourceConfiguration**：定义匹配转换源外观的配置。

## 符合

- 比特可复制
- 可复制
- 等价
- 可散列
- 可发送
- 可发送元类型


---
source: https://developer.apple.com/documentation/swiftui/transitionphase
crawled: 2025-12-04T13:16:10Z
---

# TransitionPhase

**Enumeration**

An indication of which the current stage of a transition.

## Declaration

```swift
@frozen enum TransitionPhase
```

## Overview

When a view is appearing with a transition, the transition will first be shown with the `willAppear` phase, then will be immediately moved to the `identity` phase. When a view is being removed, its transition is changed from the `identity` phase to the `didDisappear` phase. If a view is removed while it is still transitioning in, then its phase will change to `didDisappear`. If a view is re-added while it is transitioning out, its phase will change back to `identity`.

In the `identity` phase, transitions should generally not make any visual change to the view they are applied to, since the transition’s view modifications in the `identity` phase will be applied to the view as long as it is visible. In the `willAppear` and `didDisappear` phases, transitions should apply a change that will be animated to create the transition. If no animatable change is applied, then the transition will be a no-op.

- See Also: `Transition`
- See Also: `AnyTransition`

## Getting the phase

- **TransitionPhase.identity**: The transition is being applied to a view that is in the view hierarchy.
- **TransitionPhase.willAppear**: The transition is being applied to a view that is about to be inserted into the view hierarchy.
- **TransitionPhase.didDisappear**: The transition is being applied to a view that has been requested to be removed from the view hierarchy.

## Getting phase characteristics

- **isIdentity**: A Boolean that indicates whether the transition should have an identity effect, i.e. not change the appearance of its view.
- **value**: A value that can be used to multiply effects that are applied differently depending on the phase.

## Defining transitions

- **transition(_:)**: Associates a transition with the view.
- **Transition**: A description of view changes to apply when a view is added to and removed from the view hierarchy.
- **TransitionProperties**: The properties a `Transition` can have.
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

- BitwiseCopyable
- Copyable
- Equatable
- Hashable
- Sendable
- SendableMetatype

