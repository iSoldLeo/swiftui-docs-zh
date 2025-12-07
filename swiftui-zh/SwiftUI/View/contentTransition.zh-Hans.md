--- 来源：https://developer.apple.com/documentation/SwiftUI/View/contentTransition(_:)

抓取时间：2025-12-02T17:34:24Z

---

# contentTransition(_:)

**实例方法**

修改视图，使其使用指定的过渡效果来动画化视图内容的变化。

## 声明

```swift
nonisolated func contentTransition(_ transition: ContentTransition) -> some View

```

## 参数

- **transition**：用于内容变化动画的过渡效果。

## 说明

此修改器允许您执行单个视图内内容变化的过渡动画。提供的 [ContentTransition](../ContentTransition.zh-Hans.md) 可以为内容变化呈现不透明度动画、内容路径变化时的插值动画，或者完全不执行任何动画。

在以下示例中，[Button](../Button.zh-Hans.md) 会更改 [Text](../Text.zh-Hans.md) 视图的颜色和字体大小。由于这两个属性都应用于文本路径，因此 [interpolate](../ContentTransition/interpolate.zh-Hans.md) 过渡效果可以在整个过渡过程中实现这些属性的渐变动画。相比之下，[opacity](../ContentTransition/opacity.zh-Hans.md) 过渡效果只会简单地在开始和结束状态之间淡入淡出。

```swift
private static let font1 = Font.system(size: 20)
private static let font2 = Font.system(size: 45)

@State private var color = Color.red
@State private var currentFont = font1

var body: some View {
    VStack {
        Text("Content transition")
            .foregroundColor(color)
            .font(currentFont)
            .contentTransition(.interpolate)
        Spacer()
        Button("Change") {
            withAnimation(Animation.easeInOut(duration: 5.0)) {
                color = (color == .red) ? .green : .red
                currentFont = (currentFont == font1) ? font2 : font1
            }
        }
    }
}
```

此示例使用持续时间为五秒的缓入缓出动画，以便更清晰地观察插值效果。下图显示了 `Text` 在动画开始、中间和结束时的状态。

要控制内容过渡是否使用 GPU 加速渲染，请设置 [contentTransitionAddsDrawingGroup](../EnvironmentValues/contentTransitionAddsDrawingGroup.zh-Hans.md) 环境变量的值。

## 定义过渡效果

- **transition(_:)**：将过渡效果与视图关联。

- **Transition**：描述视图添加到视图层次结构或从中移除时要应用的视图更改。

- **TransitionProperties**：`Transition` 可以拥有的属性。

- **TransitionPhase**：指示过渡效果的当前阶段。

- **AsymmetricTransition**：复合过渡效果，插入和移除操作使用不同的过渡效果。

- **AnyTransition**：类型擦除过渡效果。

- **contentTransition**：当前视图内容动画的方法。

- **contentTransitionAddsDrawingGroup**：一个布尔值，用于控制渲染内容过渡的视图是否使用 GPU 加速渲染。

- **ContentTransition**：一种过渡类型，应用于单个视图内的内容，而不是视图的插入或移除。

- **PlaceholderContentView**：用于构造内联修饰符、过渡或其他辅助类型的占位符。

- **navigationTransition(_:)**：设置此视图的导航过渡样式。

- **NavigationTransition**：定义导航到视图时要使用的过渡的类型。

- **matchedTransitionSource(id:in:)**：将此视图标识为导航过渡（例如缩放过渡）的源。

- **matchedTransitionSource(id:in:configuration:)**：将此视图标识为导航过渡（例如缩放过渡）的源。

- **MatchedTransitionSourceConfiguration**：定义匹配的过渡源外观的配置。


---
source: https://developer.apple.com/documentation/SwiftUI/View/contentTransition(_:)
crawled: 2025-12-02T17:34:24Z
---

# contentTransition(_:)

**Instance Method**

Modifies the view to use a given transition as its method of animating changes to the contents of its views.

## Declaration

```swift
nonisolated func contentTransition(_ transition: ContentTransition) -> some View

```

## Parameters

- **transition**: The transition to apply when animating the content change.

## Discussion

This modifier allows you to perform a transition that animates a change within a single view. The provided [ContentTransition](../ContentTransition.zh-Hans.md) can present an opacity animation for content changes, an interpolated animation of the content’s paths as they change, or perform no animation at all.



In the following example, a [Button](../Button.zh-Hans.md) changes the color and font size of a [Text](../Text.zh-Hans.md) view. Since both of these properties apply to the paths of the text, the [interpolate](../ContentTransition/interpolate.zh-Hans.md) transition can animate a gradual change to these properties through the entire transition. By contrast, the [opacity](../ContentTransition/opacity.zh-Hans.md) transition would simply fade between the start and end states.

```swift
private static let font1 = Font.system(size: 20)
private static let font2 = Font.system(size: 45)

@State private var color = Color.red
@State private var currentFont = font1

var body: some View {
    VStack {
        Text("Content transition")
            .foregroundColor(color)
            .font(currentFont)
            .contentTransition(.interpolate)
        Spacer()
        Button("Change") {
            withAnimation(Animation.easeInOut(duration: 5.0)) {
                color = (color == .red) ? .green : .red
                currentFont = (currentFont == font1) ? font2 : font1
            }
        }
    }
}
```

This example uses an ease-in–ease-out animation with a five-second duration to make it easier to see the effect of the interpolation. The figure below shows the `Text` at the beginning of the animation, halfway through, and at the end.



To control whether content transitions use GPU-accelerated rendering, set the value of the [contentTransitionAddsDrawingGroup](../EnvironmentValues/contentTransitionAddsDrawingGroup.zh-Hans.md) environment variable.

## Defining transitions

- **transition(_:)**: Associates a transition with the view.
- **Transition**: A description of view changes to apply when a view is added to and removed from the view hierarchy.
- **TransitionProperties**: The properties a `Transition` can have.
- **TransitionPhase**: An indication of which the current stage of a transition.
- **AsymmetricTransition**: A composite `Transition` that uses a different transition for insertion versus removal.
- **AnyTransition**: A type-erased transition.
- **contentTransition**: The current method of animating the contents of views.
- **contentTransitionAddsDrawingGroup**: A Boolean value that controls whether views that render content transitions use GPU-accelerated rendering.
- **ContentTransition**: A kind of transition that applies to the content within a single view, rather than to the insertion or removal of a view.
- **PlaceholderContentView**: A placeholder used to construct an inline modifier, transition, or other helper type.
- **navigationTransition(_:)**: Sets the navigation transition style for this view.
- **NavigationTransition**: A type that defines the transition to use when navigating to a view.
- **matchedTransitionSource(id:in:)**: Identifies this view as the source of a navigation transition, such as a zoom transition.
- **matchedTransitionSource(id:in:configuration:)**: Identifies this view as the source of a navigation transition, such as a zoom transition.
- **MatchedTransitionSourceConfiguration**: A configuration that defines the appearance of a matched transition source.

