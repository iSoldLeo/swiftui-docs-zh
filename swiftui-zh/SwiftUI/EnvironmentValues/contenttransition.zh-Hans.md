---
来源： https://developer.apple.com/documentation/swiftui/environmentvalues/contenttransition
抓取时间： 2025-12-04T13:10:34Z
---

# contentTransition

**实例属性**

视图内容动画的当前方法。

## 声明

```swift
var contentTransition: ContentTransition { get set }
```

## 定义过渡

- **transition(_:)**：将过渡关联到视图。
- **Transition**：当视图添加到视图层次结构或从视图层次结构中移除视图时要应用的视图更改描述。
- **TransitionProperties**：`Transition`可具有的属性。
- **TransitionPhase**：表示过渡的当前阶段。
- **AsymmetricTransition**：一个复合`Transition`，在插入和删除时使用不同的转换。
- **AnyTransition**：类型抹除的转换。
- **contentTransition(_:)**：修改视图，使其使用给定的转换作为其视图内容变化的动画方法。
- **contentTransitionAddsDrawingGroup**：布尔值，用于控制渲染内容转换的视图是否使用 GPU 加速渲染。
- **ContentTransition**：一种过渡，适用于单个视图中的内容，而不是视图的插入或移除。
- **PlaceholderContentView**：用于构建内联修饰符、转换或其他辅助类型的占位符。
- **navigationTransition(_:)**：为该视图设置导航过渡样式。
- **NavigationTransition**：定义导航到视图时使用的过渡类型。
- **matchedTransitionSource(id:in:)**：将此视图标识为导航转换（如缩放转换）的源。
- **matchedTransitionSource(id:in:configuration:)**：将此视图标识为导航转换（如缩放转换）的源。
- **MatchedTransitionSourceConfiguration**：定义匹配转换源外观的配置。


---
source: https://developer.apple.com/documentation/swiftui/environmentvalues/contenttransition
crawled: 2025-12-04T13:10:34Z
---

# contentTransition

**Instance Property**

The current method of animating the contents of views.

## Declaration

```swift
var contentTransition: ContentTransition { get set }
```

## Defining transitions

- **transition(_:)**: Associates a transition with the view.
- **Transition**: A description of view changes to apply when a view is added to and removed from the view hierarchy.
- **TransitionProperties**: The properties a `Transition` can have.
- **TransitionPhase**: An indication of which the current stage of a transition.
- **AsymmetricTransition**: A composite `Transition` that uses a different transition for insertion versus removal.
- **AnyTransition**: A type-erased transition.
- **contentTransition(_:)**: Modifies the view to use a given transition as its method of animating changes to the contents of its views.
- **contentTransitionAddsDrawingGroup**: A Boolean value that controls whether views that render content transitions use GPU-accelerated rendering.
- **ContentTransition**: A kind of transition that applies to the content within a single view, rather than to the insertion or removal of a view.
- **PlaceholderContentView**: A placeholder used to construct an inline modifier, transition, or other helper type.
- **navigationTransition(_:)**: Sets the navigation transition style for this view.
- **NavigationTransition**: A type that defines the transition to use when navigating to a view.
- **matchedTransitionSource(id:in:)**: Identifies this view as the source of a navigation transition, such as a zoom transition.
- **matchedTransitionSource(id:in:configuration:)**: Identifies this view as the source of a navigation transition, such as a zoom transition.
- **MatchedTransitionSourceConfiguration**: A configuration that defines the appearance of a matched transition source.

