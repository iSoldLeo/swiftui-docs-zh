--- 来源：https://developer.apple.com/documentation/SwiftUI/View/navigationTransition(_:)

抓取时间：2025-12-02T17:24:50Z

---

# navigationTransition(_:)

**实例方法**

设置此视图的导航过渡样式。

## 声明

```swift
nonisolated func navigationTransition(_ style: some NavigationTransition) -> some View

```

## 说明

将此修饰符添加到位于 [NavigationStack](../NavigationStack.zh-Hans.md) 或工作表内，且不在任何容器（例如 [VStack](../VStack.zh-Hans.md)）之外的视图。

```swift
struct ContentView: View {
    @Namespace private var namespace
    var body: some View {
        NavigationStack {
            NavigationLink {
                DetailView()
                    .navigationTransition(.zoom(sourceID: "world", in: namespace))
            } label: {
                Image(systemName: "globe")
                    .matchedTransitionSource(id: "world", in: namespace)
            }
        }
    }
}
```

## 定义过渡

- **transition(_:)**：将过渡效果与视图关联。

- **Transition**：视图添加到视图层次结构或从中移除时要应用的视图更改的描述。

- **TransitionProperties**：`Transition` 可以拥有的属性。

- **TransitionPhase**：指示当前转换阶段。

- **AsymmetricTransition**：复合 `Transition`，插入和移除操作使用不同的转换。

- **AnyTransition**：类型擦除转换。

- **contentTransition(_:)**：修改视图，使其使用给定的转换作为其内容更改动画的方法。

- **contentTransition**：当前视图内容动画的方法。

- **contentTransitionAddsDrawingGroup**：一个布尔值，用于控制渲染内容过渡的视图是否使用 GPU 加速渲染。

- **ContentTransition**：一种过渡类型，应用于单个视图内的内容，而不是视图的插入或移除。

- **PlaceholderContentView**：用于构造内联修饰符、过渡或其他辅助类型的占位符。

- **NavigationTransition**：定义导航到视图时要使用的过渡的类型。

- **matchedTransitionSource(id:in:)**：将此视图标识为导航过渡（例如缩放过渡）的源。

- **matchedTransitionSource(id:in:configuration:)**：将此视图标识为导航过渡（例如缩放过渡）的源。

- **MatchedTransitionSourceConfiguration**：用于定义匹配的过渡源外观的配置。


---
source: https://developer.apple.com/documentation/SwiftUI/View/navigationTransition(_:)
crawled: 2025-12-02T17:24:50Z
---

# navigationTransition(_:)

**Instance Method**

Sets the navigation transition style for this view.

## Declaration

```swift
nonisolated func navigationTransition(_ style: some NavigationTransition) -> some View

```

## Discussion

Add this modifier to a view that appears within a [NavigationStack](../NavigationStack.zh-Hans.md) or a sheet, outside of any containers such as [VStack](../VStack.zh-Hans.md).

```swift
struct ContentView: View {
    @Namespace private var namespace
    var body: some View {
        NavigationStack {
            NavigationLink {
                DetailView()
                    .navigationTransition(.zoom(sourceID: "world", in: namespace))
            } label: {
                Image(systemName: "globe")
                    .matchedTransitionSource(id: "world", in: namespace)
            }
        }
    }
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
- **NavigationTransition**: A type that defines the transition to use when navigating to a view.
- **matchedTransitionSource(id:in:)**: Identifies this view as the source of a navigation transition, such as a zoom transition.
- **matchedTransitionSource(id:in:configuration:)**: Identifies this view as the source of a navigation transition, such as a zoom transition.
- **MatchedTransitionSourceConfiguration**: A configuration that defines the appearance of a matched transition source.

