--- 来源：https://developer.apple.com/documentation/SwiftUI/Declaring-a-Custom-View

抓取时间：2025-12-02T16:01:52Z

---

# 声明自定义视图

**Article**

定义视图并将其组装成视图层级结构。

## 概述

SwiftUI 提供了一种声明式的用户界面设计方法。传统的命令式方法要求控制器代码不仅要实例化、布局和配置视图，还要根据情况变化不断更新视图。相比之下，声明式方法通过声明视图层级结构来创建用户界面的轻量级描述，该层级结构反映了所需的界面布局。SwiftUI 会根据用户输入或状态变化等事件来管理视图的绘制和更新。

SwiftUI 提供了用于定义和配置用户界面视图的工具。您可以使用 SwiftUI 提供的内置视图以及您已定义的其他复合视图来构建自定义视图。您可以使用视图修饰符配置这些视图，并将它们连接到您的数据模型。然后，您可以将自定义视图放置在应用程序的视图层级结构中。

### 遵循视图协议

通过定义一个符合 [View](View.zh-Hans.md) 协议的结构来声明自定义视图类型：

```swift
struct MyView: View {
}
```

与其他协议（例如 [https://docs.swift.org/swift-book/LanguageGuide/Protocols.html]）一样，[View](View.zh-Hans.md) 协议为功能提供了一个蓝图——在本例中，指的是 SwiftUI 在屏幕上绘制的元素的行为。遵循该协议意味着视图必须满足一些要求，并且该协议提供了相应的功能。满足这些要求后，您可以将自定义视图插入到视图层级结构中，使其成为应用程序用户界面的一部分。

### 声明 body 属性

[View](View.zh-Hans.md) 协议的主要要求是，遵循该协议的类型必须定义一个 [body-8kl5o](View/body-8kl5o.zh-Hans.md) [https://docs.swift.org/swift-book/LanguageGuide/Properties.html#ID259]：

```swift
struct MyView: View {
    var body: some View {
    }
}
```

SwiftUI 会在需要更新视图时读取此属性的值，这在视图的生命周期内可能会重复发生，通常是响应用户输入或系统事件。视图返回的值是 SwiftUI 在屏幕上绘制的元素。

[View](View.zh-Hans.md) 协议的次要要求是，遵循该协议的类型必须为 body 属性指定一个 [https://docs.swift.org/swift-book/LanguageGuide/Generics.html#ID189]。但是，您无需显式声明。相反，您需要使用 `some View` 语法将 body 属性声明为 [https://docs.swift.org/swift-book/LanguageGuide/OpaqueTypes.html]，仅表明 body 的类型符合 [View](View.zh-Hans.md)。具体类型取决于 body 的内容，而内容会随着您在开发过程中编辑 body 而变化。Swift 会自动推断具体类型。

### 构建视图内容

通过向视图的 body 属性添加内容来描述视图的外观。您可以从 SwiftUI 提供的内置视图以及您在其他地方定义的自定义视图来构建 body。例如，您可以创建一个 body 来绘制字符串“Hello, World!”使用内置的 [Text](Text.zh-Hans.md) 视图：

```swift
struct MyView: View {
    var body: some View {
        Text("Hello, World!")
    }
}
```

除了用于特定类型内容、控件和指示器的视图（例如 [Text](Text.zh-Hans.md)、[Toggle](Toggle.zh-Hans.md) 和 [ProgressView](ProgressView.zh-Hans.md)）之外，SwiftUI 还提供了可用于排列其他视图的内置视图。例如，您可以使用 [VStack](VStack.zh-Hans.md) 将两个 [Text](Text.zh-Hans.md) 视图垂直堆叠：

```swift
struct MyView: View {
    var body: some View {
        VStack {
            Text("Hello, World!")
            Text("Glad to meet you.")
        }
    }
}
```

像上面示例中的堆栈一样，带有多个输入子视图的视图通常使用带有 [ViewBuilder](ViewBuilder.zh-Hans.md) 属性的闭包来实现。这支持多语句闭包，无需在调用处添加额外的语法。您只需按顺序列出输入视图即可。

有关包含其他视图的视图示例，请参阅 [Layout-fundamentals](Layout-fundamentals.zh-Hans.md)。

### 使用修饰符配置视图

要配置视图主体中的视图，您需要应用视图修饰符。修饰符实际上就是对特定视图调用的方法。该方法会返回一个新的、经过修改的视图，该视图会有效地替换视图层次结构中的原始视图。

SwiftUI 扩展了 [View](View.zh-Hans.md) 协议，并为此提供了一系列方法。所有遵循 [View](View.zh-Hans.md) 协议的视图（包括内置视图和自定义视图）都可以访问这些方法，以某种方式改变视图的行为。例如，您可以通过应用 [font(_:)](View/font.zh-Hans.md) 修饰符来更改文本视图的字体：

```swift
struct MyView: View {
    var body: some View {
        VStack {
            Text("Hello, World!")
                .font(.title)
            Text("Glad to meet you.")
        }
    }
}
```

有关视图修饰符的工作原理以及如何在视图中使用它们的更多信息，请参阅 [Configuring-Views](Configuring-Views.zh-Hans.md)。

### 管理数据

要为视图提供输入，请添加属性。例如，您可以使“Hello, World!”字符串的字体可配置：

```swift
struct MyView: View {
    let helloFont: Font
    
    var body: some View {
        VStack {
            Text("Hello, World!")
                .font(helloFont)
            Text("Glad to meet you.")
        }
    }
}
```

如果输入值发生更改，SwiftUI 会检测到此更改，并仅重新绘制界面中受影响的部分。这可能涉及重新初始化整个视图，但 SwiftUI 会为您管理此过程。

由于系统可能随时重新初始化视图，因此务必避免在视图的初始化代码中执行任何重要的操作。通常最好省略显式初始化器，如上例所示，这样 Swift 就可以自动合成一个*成员级初始化器*。

SwiftUI 提供了许多工具来帮助你在这些限制条件下管理应用程序的数据，如 [Model-data](Model-data.zh-Hans.md) 中所述。有关 Swift 初始化器的更多信息，请参阅《Swift 程序设计语言》中的 [https://docs.swift.org/swift-book/LanguageGuide/Initialization.html]。

### 将视图添加到视图层次结构中

定义视图后，你可以像使用内置视图一样将其添加到其他视图中。只需在视图层次结构中你希望它出现的位置声明它即可。例如，您可以将 `MyView` 放入应用程序的 `ContentView` 中，Xcode 会自动将其创建为新应用程序的根视图：

```swift
struct ContentView: View {
    var body: some View {
        MyView(helloFont: .title)
    }
}
```

或者，您可以将视图添加为应用程序中新场景的根视图，例如声明 macOS 偏好设置窗口内容的 [Settings](Settings.zh-Hans.md) 场景，或声明 watchOS 通知内容的 [WKNotificationScene](WKNotificationScene.zh-Hans.md) 场景。有关使用 SwiftUI 定义应用程序结构的更多信息，请参阅 [App-organization](App-organization.zh-Hans.md)。

## 创建视图

- **View**：一种表示应用程序用户界面一部分的类型，并提供用于配置视图的修饰符。

- **ViewBuilder**：一个自定义参数属性，用于从闭包构建视图。


---
source: https://developer.apple.com/documentation/SwiftUI/Declaring-a-Custom-View
crawled: 2025-12-02T16:01:52Z
---

# Declaring a custom view

**Article**

Define views and assemble them into a view hierarchy.

## Overview

SwiftUI offers a declarative approach to user interface design. With a traditional imperative approach, the burden is on your controller code not only to instantiate, lay out, and configure views, but also to continually make updates as conditions change. In contrast, with a declarative approach, you create a lightweight description of your user interface by declaring views in a hierarchy that mirrors the desired layout of your interface. SwiftUI then manages drawing and updating these views in response to events like user input or state changes.



SwiftUI provides tools for defining and configuring the views in your user interface. You compose custom views out of built-in views that SwiftUI provides, plus other composite views that you’ve already defined. You configure these views with view modifiers and connect them to your data model. You then place your custom views within your app’s view hierarchy.

### Conform to the view protocol

Declare a custom view type by defining a structure that conforms to the [View](View.zh-Hans.md) protocol:

```swift
struct MyView: View {
}
```

Like other [https://docs.swift.org/swift-book/LanguageGuide/Protocols.html], the [View](View.zh-Hans.md) protocol provides a blueprint for functionality — in this case, the behavior of an element that SwiftUI draws onscreen. Conformance to the protocol comes with both requirements that a view must fulfill, and functionality that the protocol provides. After you fulfill the requirements, you can insert your custom view into a view hierarchy so that it becomes part of your app’s user interface.

### Declare a body

The [View](View.zh-Hans.md) protocol’s main requirement is that conforming types must define a [body-8kl5o](View/body-8kl5o.zh-Hans.md) [https://docs.swift.org/swift-book/LanguageGuide/Properties.html#ID259]:

```swift
struct MyView: View {
    var body: some View {
    }
}
```

SwiftUI reads the value of this property any time it needs to update the view, which can happen repeatedly during the life of the view, typically in response to user input or system events. The value that the view returns is an element that SwiftUI draws onscreen.

The [View](View.zh-Hans.md) protocol’s secondary requirement is that conforming types must indicate an [https://docs.swift.org/swift-book/LanguageGuide/Generics.html#ID189] for the body property. However, you don’t make an explicit declaration. Instead, you declare the body property as an [https://docs.swift.org/swift-book/LanguageGuide/OpaqueTypes.html], using the `some View` syntax, to indicate only that the body’s type conforms to [View](View.zh-Hans.md). The exact type depends on the body’s content, which varies as you edit the body during development. Swift infers the exact type automatically.

### Assemble the view’s content

Describe your view’s appearance by adding content to the view’s body property. You can compose the body from built-in views that SwiftUI provides, as well as custom views that you’ve defined elsewhere. For example, you can create a body that draws the string “Hello, World!” using a built-in [Text](Text.zh-Hans.md) view:

```swift
struct MyView: View {
    var body: some View {
        Text("Hello, World!")
    }
}
```



In addition to views for specific kinds of content, controls, and indicators, like [Text](Text.zh-Hans.md), [Toggle](Toggle.zh-Hans.md), and [ProgressView](ProgressView.zh-Hans.md), SwiftUI also provides built-in views that you can use to arrange other views. For example, you can vertically stack two [Text](Text.zh-Hans.md) views using a [VStack](VStack.zh-Hans.md):

```swift
struct MyView: View {
    var body: some View {
        VStack {
            Text("Hello, World!")
            Text("Glad to meet you.")
        }
    }
}
```



Views that take multiple input child views, like the stack in the example above, typically do so using a closure marked with the [ViewBuilder](ViewBuilder.zh-Hans.md) attribute. This enables a multiple-statement closure that doesn’t require additional syntax at the call site. You only need to list the input views in succession.

For examples of views that contain other views, see [Layout-fundamentals](Layout-fundamentals.zh-Hans.md).

### Configure views with modifiers

To configure the views in your view’s body, you apply view modifiers. A modifier is nothing more than a method called on a particular view. The method returns a new, altered view that effectively takes the place of the original in the view hierarchy.

SwiftUI extends the [View](View.zh-Hans.md) protocol with a large set of methods for this purpose. All [View](View.zh-Hans.md) protocol conformers — both built-in and custom views — have access to these methods that alter the behavior of a view in some way. For example, you can change the font of a text view by applying the [font(_:)](View/font.zh-Hans.md) modifier:

```swift
struct MyView: View {
    var body: some View {
        VStack {
            Text("Hello, World!")
                .font(.title)
            Text("Glad to meet you.")
        }
    }
}
```



For more information about how view modifiers work, and how to use them on your views, see [Configuring-Views](Configuring-Views.zh-Hans.md).

### Manage data

To supply inputs to your views, add properties. For example, you can make the font of the “Hello, World!” string configurable:

```swift
struct MyView: View {
    let helloFont: Font
    
    var body: some View {
        VStack {
            Text("Hello, World!")
                .font(helloFont)
            Text("Glad to meet you.")
        }
    }
}
```

If an input value changes, SwiftUI notices the change and redraws only the affected parts of your interface. This might involve reinitializing your entire view, but SwiftUI manages that for you.

Because the system may reinitialize a view at any time, it’s important to avoid doing any significant work in your view’s initialization code. It’s often best to omit an explicit initializer, as in the example above, allowing Swift to synthesize a *member-wise initializer* instead.

SwiftUI provides many tools to help you manage your app’s data under these constraints, as described in [Model-data](Model-data.zh-Hans.md). For information about Swift initializers, see [https://docs.swift.org/swift-book/LanguageGuide/Initialization.html] in *The Swift Programming Language*.

### Add your view to the view hierarchy

After you define a view, you can incorporate it in other views, just like you do with built-in views. You add your view by declaring it at the point in the hierarchy at which you want it to appear. For example, you could put `MyView` in your app’s `ContentView`, which Xcode creates automatically as the root view of a new app:

```swift
struct ContentView: View {
    var body: some View {
        MyView(helloFont: .title)
    }
}
```

Alternatively, you could add your view as the root view of a new scene in your app, like the [Settings](Settings.zh-Hans.md) scene that declares content for a macOS preferences window, or a [WKNotificationScene](WKNotificationScene.zh-Hans.md) scene that declares the content for a watchOS notification. For more information about defining your app structure with SwiftUI, see [App-organization](App-organization.zh-Hans.md).

## Creating a view

- **View**: A type that represents part of your app’s user interface and provides modifiers that you use to configure views.
- **ViewBuilder**: A custom parameter attribute that constructs views from closures.

