--- 来源：https://developer.apple.com/documentation/SwiftUI/View/matchedTransitionSource(id:in:configuration:)

抓取时间：2025-11-30T21:09:52Z

---

# matchedTransitionSource(id:in:configuration:)

**实例方法**

将此视图标识为导航过渡（例如缩放过渡）的源。

## 声明

```swift
nonisolated func matchedTransitionSource(id: some Hashable, in namespace: Namespace.ID, configuration: (EmptyMatchedTransitionSourceConfiguration) -> some MatchedTransitionSourceConfiguration) -> some View

```

## 参数

- **id**：标识符，通常派生自视图所显示数据的标识符。

- **namespace**：定义 `id` 的命名空间。通过将 [Namespace](../Namespace.zh-Hans.md) 变量添加到 [View](../View.zh-Hans.md) 类型，并在视图的 body 方法中读取其值，即可创建新的命名空间。

- **configuration**：可用于为源应用样式的闭包。

## 讨论

可以使用 `configuration` 尾部闭包配置源的外观。当缩放过渡源自此匹配的过渡源时，应用的任何修饰符都将平滑插值。

```swift
MyView()
    .matchedTransitionSource(id: someID, in: someNamespace) { source in
        source
            .cornerRadius(8.0)
    }
```

## 定义过渡

- **transition(_:)**：将过渡与视图关联。

- **Transition**：描述在视图添加到视图层次结构和从视图层次结构中移除时要应用的视图更改。

- **TransitionProperties**：`Transition` 可以拥有的属性。

- **TransitionPhase**：指示过渡的当前阶段。

- **AsymmetricTransition**：复合 `Transition`，插入和删除使用不同的过渡效果。

- **AnyTransition**：类型擦除过渡。

- **contentTransition(_:)**：修改视图，使其使用指定的过渡效果作为视图内容更改的动画方法。

- **contentTransition**：视图内容的当前动画方法。

- **contentTransitionAddsDrawingGroup**：一个布尔值，用于控制渲染内容过渡的视图是否使用 GPU 加速渲染。

- **ContentTransition**：一种应用于单个视图内内容的过渡效果，而非视图的插入或移除。

- **PlaceholderContentView**：用于构建内联修饰符、过渡效果或其他辅助类型的占位符。

- **navigationTransition(_:)**：设置此视图的导航过渡样式。

- **NavigationTransition**：定义导航到视图时使用的过渡效果的类型。

- **matchedTransitionSource(id:in:)**：将此视图标识为导航过渡效果（例如缩放过渡效果）的源。

- **MatchedTransitionSourceConfiguration**：定义匹配的过渡源外观的配置。


---
source: https://developer.apple.com/documentation/SwiftUI/View/matchedTransitionSource(id:in:configuration:)
crawled: 2025-11-30T21:09:52Z
---

# matchedTransitionSource(id:in:configuration:)

**Instance Method**

Identifies this view as the source of a navigation transition, such as a zoom transition.

## Declaration

```swift
nonisolated func matchedTransitionSource(id: some Hashable, in namespace: Namespace.ID, configuration: (EmptyMatchedTransitionSourceConfiguration) -> some MatchedTransitionSourceConfiguration) -> some View

```

## Parameters

- **id**: The identifier, often derived from the identifier of the data being displayed by the view.
- **namespace**: The namespace in which defines the `id`. New namespaces are created by adding an [Namespace](../Namespace.zh-Hans.md) variable to a [View](../View.zh-Hans.md) type and reading its value in the view’s body method.
- **configuration**: A closure that you can use to apply styling to the source.

## Discussion

The appearance of the source can be configured using the `configuration` trailing closure. Any modifiers applied will be smoothly interpolated when a zoom transition originates from this matched transition source.

```swift
MyView()
    .matchedTransitionSource(id: someID, in: someNamespace) { source in
        source
            .cornerRadius(8.0)
    }
```

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
- **MatchedTransitionSourceConfiguration**: A configuration that defines the appearance of a matched transition source.

