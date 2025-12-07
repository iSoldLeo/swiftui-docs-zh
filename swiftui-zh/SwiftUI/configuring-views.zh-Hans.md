---
来源： https://developer.apple.com/documentation/swiftui/configuring-views
抓取时间： 2025-12-02T17:47:16Z
---

# 配置视图

**Article**

通过应用视图修饰符调整视图的特性。

### 概览

在 SwiftUI 中，您可以将视图组合成一个层次结构来描述应用程序的用户界面。为了帮助您自定义应用程序视图的外观和行为，您可以使用*视图修饰符*。例如，您可以使用修改器来

- 为视图添加辅助功能。
- 调整视图的样式、布局和其他外观特征。
- 响应事件，如复制和粘贴。
- 有条件地显示模式视图，如弹出窗口。
- 配置工具栏等辅助视图。

由于视图修改器是 Swift 方法，其行为由[View](View.zh-Hans.md) 协议提供，因此你可以将它们应用于任何符合[View](View.zh-Hans.md) 协议的类型。这包括内置视图，如[Text](Text.zh-Hans.md)、[Image](Image.zh-Hans.md) 和[Button](Button.zh-Hans.md)，以及您定义的视图。

### 使用修饰符配置视图

与其他 Swift 方法一样，修改器也会对实例（这里是某种视图）进行操作，并可选择接受输入参数。例如，您可以使用[foregroundColor(_:)](View/foregroundColor.zh-Hans.md)修改器来设置⟦视图的颜色：

```swift
Text("Hello, World!")
    .foregroundColor(.red) // Display red text.
```

修改器会返回一个视图，该视图会封装原始视图，并在视图层次结构中取代原始视图。可以将上例中的两行视图视为解析为显示红色文本的单一视图。



虽然上面的代码遵循 Swift 的规则，但对于刚接触 SwiftUI 的开发人员来说，代码的结构可能并不熟悉。SwiftUI 使用声明式方法，即在代码中与视图在视图层次结构中的位置相对应的位置声明和配置视图。有关详细信息，请参见 [Declaring-a-Custom-View](Declaring-a-Custom-View.zh-Hans.md)。

### 链接修改器以实现复杂效果

通过一个接一个地调用修饰符，通常可以连锁修饰符，每个修饰符都会包装前一个修饰符的结果。例如，您可以使用[frame(width:height:alignment:)](View/frame_width_height_alignment.zh-Hans.md)修改器将文本视图包裹在一个给定宽度的隐形框中，以影响其布局，然后使用[border(_:width:)](View/border___width.zh-Hans.md)修改器在其周围绘制轮廓：

```swift
Text("Title")
    .frame(width: 100)
    .border(Color.gray)
```

应用修改器的顺序很重要。例如，上述代码产生的边框会勾勒出整个框架的宽度。



通过在边框修饰符之后指定框架修饰符，SwiftUI 只在文本视图中应用边框，而文本视图所占用的空间永远不会超过渲染其内容所需的空间。

```swift
Text("Title")
    .border(Color.gray) // Apply the border first this time.
    .frame(width: 100)
```

将该视图包裹在宽度为固定 100 点的不可见视图中会影响复合视图的布局，但对边框没有影响。



### 配置子视图

您可以将[View](View.zh-Hans.md) 协议定义的任何视图修改器应用于任何具体视图，即使该修改器不会对目标视图产生直接影响。修改器的效果会传播给没有明确覆盖修改器的子视图。

例如，[VStack](VStack.zh-Hans.md) 实例本身只起到垂直堆叠其他视图的作用，并不显示任何文本。因此，对堆叠应用[font(_:)](View/font.zh-Hans.md)修饰符对堆叠没有任何影响。然而，字体修改器确实适用于堆栈的任何子视图，其中一些视图可能会显示文本。不过，您可以在特定子视图中添加另一个修改器，从而在本地覆盖堆栈的修改器：

```swift
VStack {
    Text("Title")
        .font(.title) // Override the font of this view.
    Text("First body line.")
    Text("Second body line.")
}
.font(.body) // Set a default font for text in the stack.
```



### 使用特定于视图的修饰符

虽然许多视图类型都依赖标准视图修饰符来进行自定义和控制，但有些视图确实定义了该视图类型专用的修饰符。除了相应的视图类型外，您不能在其他任何视图上使用此类修改器。例如，[Text](Text.zh-Hans.md) 定义了[bold()](Text/bold.zh-Hans.md) 修饰符，以便为视图文本添加粗体效果。由于[font(_:)](View/font.zh-Hans.md) 是[View](View.zh-Hans.md) 协议的一部分，因此可以在任何视图中使用[font(_:)](View/font.zh-Hans.md)，但只能在[Text](Text.zh-Hans.md) 视图中使用[bold()](Text/bold.zh-Hans.md)。因此，不能在容器视图中使用：

```swift
VStack {
    Text("Hello, world!")
}
.bold() // Fails because 'VStack' doesn't have a 'bold' modifier.
```

在应用另一个通用修饰符后，也不能在[Text](Text.zh-Hans.md) 视图上使用该修饰符，因为通用修饰符会返回 [https://docs.swift.org/swift-book/LanguageGuide/OpaqueTypes.html]。例如，padding 修饰符的返回值不是[Text](Text.zh-Hans.md)，而是一个不透明的结果类型，不能使用粗体修饰符：

```swift
Text("Hello, world!")
    .padding()
    .bold() // Fails because 'some View' doesn't have a 'bold' modifier.
```

取而代之的是，直接在[Text](Text.zh-Hans.md) 视图中应用粗体修饰符，然后添加填充：

```swift
Text("Hello, world!")
    .bold() // Succeeds.
    .padding()
```

## 修改视图

- 减少视图修改器的维护**：将经常重复使用的视图修改器捆绑到自定义视图修改器中。
- **modifier(_:)**：将修改器应用到视图并返回新视图。
- **ViewModifier**：将修改器应用到视图或其他视图修改器，生成原始值的不同版本。
- **EmptyModifier**：空修饰符或标识修饰符，在开发过程中用于在编译时切换修饰符。
- **ModifiedContent**：应用了修饰符的值。
- **EnvironmentalModifier**：在使用前必须在环境中解析为具体修饰符的修饰符。
- **ManipulableModifier**：修饰符。
- **ManipulableResponderModifier**：修饰语。
- **ManipulableTransformBindingModifier**
- **ManipulationGeometryModifier**
- **ManipulationGestureModifier**
- **ManipulationUsingGestureStateModifier**
- **Manipulable**：各种可操作相关类型的命名空间。


---
source: https://developer.apple.com/documentation/swiftui/configuring-views
crawled: 2025-12-02T17:47:16Z
---

# Configuring views

**Article**

Adjust the characteristics of a view by applying view modifiers.

## Overview

In SwiftUI, you assemble views into a hierarchy that describes your app’s user interface. To help you customize the appearance and behavior of your app’s views, you use *view modifiers*. For example, you can use modifiers to:

- Add accessibility features to a view.
- Adjust a view’s styling, layout, and other appearance characteristics.
- Respond to events, like copy and paste.
- Conditionally present modal views, like popovers.
- Configure supporting views, like toolbars.

Because view modifiers are Swift methods with behavior provided by the [View](View.zh-Hans.md) protocol, you can apply them to any type that conforms to the [View](View.zh-Hans.md) protocol. That includes built-in views like [Text](Text.zh-Hans.md), [Image](Image.zh-Hans.md), and [Button](Button.zh-Hans.md), as well as views that you define.

### Configure a view with a modifier

Like other Swift methods, a modifier operates on an instance — a view of some kind in this case — and can optionally take input parameters. For example, you can apply the [foregroundColor(_:)](View/foregroundColor.zh-Hans.md) modifier to set the color of a [Text](Text.zh-Hans.md) view:

```swift
Text("Hello, World!")
    .foregroundColor(.red) // Display red text.
```

Modifiers return a view that wraps the original view and replaces it in the view hierarchy. You can think of the two lines in the example above as resolving to a single view that displays red text.



While the code above follows the rules of Swift, the code’s structure might be unfamiliar for developers new to SwiftUI. SwiftUI uses a declarative approach, where you declare and configure a view at the point in your code that corresponds to the view’s position in the view hierarchy. For more information, see [Declaring-a-Custom-View](Declaring-a-Custom-View.zh-Hans.md).

### Chain modifiers to achieve complex effects

You commonly chain modifiers, each wrapping the result of the previous one, by calling them one after the other. For example, you can wrap a text view in an invisible box with a given width using the [frame(width:height:alignment:)](View/frame_width_height_alignment.zh-Hans.md) modifier to influence its layout, and then use the [border(_:width:)](View/border___width.zh-Hans.md) modifier to draw an outline around that:

```swift
Text("Title")
    .frame(width: 100)
    .border(Color.gray)
```

The order in which you apply modifiers matters. For example, the border that results from the code above outlines the full width of the frame.



By specifying the frame modifier after the border modifier, SwiftUI applies the border only to the text view, which never takes more space than it needs to render its contents.

```swift
Text("Title")
    .border(Color.gray) // Apply the border first this time.
    .frame(width: 100)
```

Wrapping that view in an invisible one with a fixed 100 point width affects the layout of the composite view, but has no effect on the border.



### Configure child views

You can apply any view modifier defined by the [View](View.zh-Hans.md) protocol to any concrete view, even when the modifier doesn’t have an immediate effect on its target view. The effects of a modifier propagate to child views that don’t explicitly override the modifier.

For example, a [VStack](VStack.zh-Hans.md) instance on its own acts only to vertically stack other views — it doesn’t have any text to display. Therefore, applying a [font(_:)](View/font.zh-Hans.md) modifier to the stack has no effect on the stack. Yet the font modifier does apply to any of the stack’s child views, some of which might display text. You can, however, locally override the stack’s modifier by adding another to a specific child view:

```swift
VStack {
    Text("Title")
        .font(.title) // Override the font of this view.
    Text("First body line.")
    Text("Second body line.")
}
.font(.body) // Set a default font for text in the stack.
```



### Use view-specific modifiers

While many view types rely on standard view modifiers for customization and control, some views do define modifiers that are specific to that view type. You can’t use such a modifier on anything but the appropriate kind of view. For example, [Text](Text.zh-Hans.md) defines the [bold()](Text/bold.zh-Hans.md) modifier as a convenience for adding a bold effect to the view’s text. While you can use [font(_:)](View/font.zh-Hans.md) on any view because it’s part of the [View](View.zh-Hans.md) protocol, you can use [bold()](Text/bold.zh-Hans.md) only on [Text](Text.zh-Hans.md) views. As a result, you can’t use it on a container view:

```swift
VStack {
    Text("Hello, world!")
}
.bold() // Fails because 'VStack' doesn't have a 'bold' modifier.
```

You also can’t use it on a [Text](Text.zh-Hans.md) view after applying another general modifier because general modifiers return an [https://docs.swift.org/swift-book/LanguageGuide/OpaqueTypes.html]. For example, the return value from the padding modifier isn’t [Text](Text.zh-Hans.md), but rather an opaque result type that can’t take a bold modifier:

```swift
Text("Hello, world!")
    .padding()
    .bold() // Fails because 'some View' doesn't have a 'bold' modifier.
```

Instead, apply the bold modifier directly to the [Text](Text.zh-Hans.md) view and then add the padding:

```swift
Text("Hello, world!")
    .bold() // Succeeds.
    .padding()
```

## Modifying a view

- **Reducing view modifier maintenance**: Bundle view modifiers that you regularly reuse into a custom view modifier.
- **modifier(_:)**: Applies a modifier to a view and returns a new view.
- **ViewModifier**: A modifier that you apply to a view or another view modifier, producing a different version of the original value.
- **EmptyModifier**: An empty, or identity, modifier, used during development to switch modifiers at compile time.
- **ModifiedContent**: A value with a modifier applied to it.
- **EnvironmentalModifier**: A modifier that must resolve to a concrete modifier in an environment before use.
- **ManipulableModifier**
- **ManipulableResponderModifier**
- **ManipulableTransformBindingModifier**
- **ManipulationGeometryModifier**
- **ManipulationGestureModifier**
- **ManipulationUsingGestureStateModifier**
- **Manipulable**: A namespace for various manipulable related types.

