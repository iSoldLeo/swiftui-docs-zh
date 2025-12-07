--- 来源：https://developer.apple.com/documentation/SwiftUI/View/transition(_:)

抓取时间：2025-11-30T21:19:26Z

---

# transition(_:)

**实例方法**

将过渡效果与视图关联。

## 声明

```swift
nonisolated func transition(_ t: AnyTransition) -> some View

```

## 说明

当此视图出现或消失时，将应用过渡效果，从而实现视图的动画效果。

以下代码将根据条件显示 MyView，并在其出现或消失时使用滑动过渡效果。

```swift
if isActive {
    MyView()
        .transition(.slide)
}
Button("Toggle") {
    withAnimation {
        isActive.toggle()
    }
}
```

## 定义过渡效果

- **Transition**：描述视图添加到视图层次结构或从中移除时要应用的视图更改。

- **TransitionProperties**：`Transition` 可以拥有的属性。

- **TransitionPhase**：指示过渡的当前阶段。

- **AsymmetricTransition**：复合 `Transition`，插入和删除使用不同的过渡效果。

- **AnyTransition**：类型擦除过渡。

- **contentTransition(_:)**：修改视图，使其使用指定的过渡效果作为视图内容动画的方法。

- **contentTransition**：视图内容动画的当前方法。

- **contentTransitionAddsDrawingGroup**：一个布尔值，用于控制渲染内容过渡的视图是否使用 GPU 加速渲染。

- **ContentTransition**：一种应用于单个视图内内容的过渡效果，而非视图的插入或移除。

- **PlaceholderContentView**：用于构建内联修饰符、过渡效果或其他辅助类型的占位符。

- **navigationTransition(_:)**：设置此视图的导航过渡样式。

- **NavigationTransition**：定义导航到视图时使用的过渡效果的类型。

- **matchedTransitionSource(id:in:)**：将此视图标识为导航过渡效果（例如缩放过渡效果）的源。

- **matchedTransitionSource(id:in:configuration:)**：将此视图标识为导航过渡效果（例如缩放过渡效果）的源。

- **MatchedTransitionSourceConfiguration**：定义匹配的过渡效果源的外观的配置。


---
source: https://developer.apple.com/documentation/SwiftUI/View/transition(_:)
crawled: 2025-11-30T21:19:26Z
---

# transition(_:)

**Instance Method**

Associates a transition with the view.

## Declaration

```swift
nonisolated func transition(_ t: AnyTransition) -> some View

```

## Discussion

When this view appears or disappears, the transition will be applied to it, allowing for animating it in and out.

The following code will conditionally show MyView, and when it appears or disappears, will use a slide transition to show it.

```swift
if isActive {
    MyView()
        .transition(.slide)
}
Button("Toggle") {
    withAnimation {
        isActive.toggle()
    }
}
```

## Defining transitions

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

