--- 来源：https://developer.apple.com/documentation/SwiftUI/Managing-User-Interface-State

抓取时间：2025-12-02T17:32:10Z

---

# 管理用户界面状态

**Article**

将视图特定的数据封装在应用程序的视图层级结构中，使视图可重用。

## 概述

将数据存储为状态，并将其存储在需要该数据的视图的最近公共祖先中，以建立一个跨视图共享的单一*真实数据源*。可以通过 Swift 属性以只读方式提供数据，或者使用绑定创建与状态的双向连接。SwiftUI 会监视数据的变化，并根据需要更新任何受影响的视图。

不要使用状态属性进行持久存储，因为状态变量的生命周期与视图的生命周期相同。相反，应该使用它们来管理仅影响用户界面的瞬态状态，例如按钮的高亮状态、筛选设置或当前选中的列表项。在原型设计阶段，也就是在准备好修改应用的数据模型之前，这种存储方式也非常方便。

### 将可变值作为状态进行管理

如果视图需要存储可修改的数据，请使用 [State](State.zh-Hans.md) 属性包装器声明一个变量。例如，您可以在播客播放器视图中创建一个 `isPlaying` 布尔值，用于跟踪播客的播放状态：

```swift
struct PlayerView: View {
    @State private var isPlaying: Bool = false
    
    var body: some View {
        // ...
    }
}
```

将属性标记为状态会告诉框架管理底层存储。视图通过属性名称读取和写入状态的 [wrappedValue](State/wrappedValue.zh-Hans.md) 属性中的数据。当您更改值时，SwiftUI 会更新视图中受影响的部分。例如，您可以向 `PlayerView` 添加一个按钮，点击该按钮可以切换存储的值，并根据存储的值显示不同的图像：

```swift
Button(action: {
    self.isPlaying.toggle()
}) {
    Image(systemName: isPlaying ? "pause.circle" : "play.circle")
}
```

通过将状态变量声明为私有变量来限制其作用域。这可以确保变量始终封装在声明它们的视图层级结构中。

### 声明 Swift 属性以存储不可变值

要为视图提供视图不会修改的数据，请声明一个标准的 Swift 属性。例如，您可以扩展播客播放器，使其包含一个输入结构，其中包含剧集标题和节目名称的字符串：

```swift
struct PlayerView: View {
    let episode: Episode // The queued episode.
    @State private var isPlaying: Bool = false
    
    var body: some View {
        VStack {
            // Display information about the episode.
            Text(episode.title)
            Text(episode.showTitle)

            Button(action: {
                self.isPlaying.toggle()
            }) {
                Image(systemName: isPlaying ? "pause.circle" : "play.circle")
            }
        }
    }
}
```

虽然 `PlayerView` 中 episode 属性的值是常量，但它不需要是此视图父视图中的常量。当用户在父视图中选择不同的剧集时，SwiftUI 会检测到状态变化，并使用新的输入重新创建 `PlayerView`。

### 使用绑定共享状态访问权限

如果一个视图需要与子视图共享状态控制权，请在子视图中声明一个带有 [Binding](Binding.zh-Hans.md) 属性包装器的属性。绑定表示对现有存储的引用，从而为底层数据保持单一数据源。例如，如果您将播客播放器视图的按钮重构为名为 `PlayButton` 的子视图，则可以将其绑定到 `isPlaying` 属性：

```swift
struct PlayButton: View {
    @Binding var isPlaying: Bool
    
    var body: some View {
        Button(action: {
            self.isPlaying.toggle()
        }) {
            Image(systemName: isPlaying ? "pause.circle" : "play.circle")
        }
    }
}
```

如上所示，您可以像操作状态一样，直接引用属性来读取和写入绑定的包装值。但与状态属性不同的是，绑定没有自己的存储。它引用存储在其他位置的状态属性，并提供与该存储的双向连接。

实例化 `PlayButton` 时，通过在父视图中声明的相应状态变量前加上美元符号 (`$`) 来提供绑定：

```swift
struct PlayerView: View {
    var episode: Episode
    @State private var isPlaying: Bool = false
    
    var body: some View {
        VStack {
            Text(episode.title)
            Text(episode.showTitle)
            PlayButton(isPlaying: $isPlaying) // Pass a binding.
        }
    }
}
```

`$` 前缀会向包装属性请求其 [projectedValue](State/projectedValue.zh-Hans.md)，对于状态而言，它是指向底层存储的绑定。类似地，您可以使用 `$` 前缀从绑定中获取绑定，从而允许您将绑定传递到任意数量的视图层次结构中。

您还可以获取状态变量中作用域值的绑定。例如，如果您在播放器的父视图中将 `episode` 声明为状态变量，并且剧集结构中还包含一个您想要用切换开关控制的 `isFavorite` 布尔值，那么您可以引用 `$episode.isFavorite` 来获取剧集收藏状态的绑定：

```swift
struct Podcaster: View {
    @State private var episode = Episode(title: "Some Episode",
                                         showTitle: "Great Show",
                                         isFavorite: false)
    var body: some View {
        VStack {
            Toggle("Favorite", isOn: $episode.isFavorite) // Bind to the Boolean.
            PlayerView(episode: episode)
        }
    }
}
```

### 动画化状态过渡

当视图状态发生变化时，SwiftUI 会立即更新受影响的视图。如果您想要平滑的视觉过渡，可以通过将触发过渡的状态更改包装在对 [withAnimation(_:_:)](withAnimation.zh-Hans.md) 函数的调用中，来告诉 SwiftUI 为其添加动画效果。例如，您可以为由布尔值 `isPlaying` 控制的变化添加动画效果：

```swift
withAnimation(.easeInOut(duration: 1)) {
    self.isPlaying.toggle()
}
```

通过在动画函数的尾部闭包中更改 `isPlaying`，您可以告诉 SwiftUI 为任何依赖于该值的内容添加动画效果，例如按钮图像的缩放效果：

```swift
Image(systemName: isPlaying ? "pause.circle" : "play.circle")
    .scaleEffect(isPlaying ? 1 : 1.5)
```

SwiftUI 会使用您指定的曲线和持续时间，或如果您未提供任何值，则使用合理的默认值，在 `1` 和 `1.5` 的给定值之间随时间过渡缩放效果。另一方面，即使同一个布尔值决定要显示哪个系统图像，图像内容也不会受到动画的影响。这是因为 SwiftUI 无法以有意义的方式在两个字符串 `pause.circle` 和 `play.circle` 之间进行渐进式过渡。

您可以为状态属性添加动画，或者像上面的示例一样，为绑定添加动画。无论哪种方式，SwiftUI 都会为底层存储值更改时发生的任何视图更改添加动画。例如，如果您为 `PlayerView` 添加背景颜色（位于动画块所在视图层级的上一级），SwiftUI 也会为其添加动画：

```swift
VStack {
    Text(episode.title)
    Text(episode.showTitle)
    PlayButton(isPlaying: $isPlaying)
}
.background(isPlaying ? Color.green : Color.red) // Transitions with animation.
```

如果您想将动画应用于特定视图，而不是应用于由状态更改触发的所有视图，请改用 [animation(_:value:)](View/animation___value.zh-Hans.md) 视图修饰符。

## 创建和共享视图状态

- **State**：一种属性包装类型，可以读取和写入由 SwiftUI 管理的值。

- **Bindable**：一种属性包装类型，支持创建与可观察对象可变属性的绑定。

- **Binding**：一种属性包装类型，可以读取和写入由数据源拥有的值。


---
source: https://developer.apple.com/documentation/SwiftUI/Managing-User-Interface-State
crawled: 2025-12-02T17:32:10Z
---

# Managing user interface state

**Article**

Encapsulate view-specific data within your app’s view hierarchy to make your views reusable.

## Overview

Store data as state in the least common ancestor of the views that need the data to establish a single *source of truth* that’s shared across views. Provide the data as read-only through a Swift property, or create a two-way connection to the state with a binding. SwiftUI watches for changes in the data, and updates any affected views as needed.



Don’t use state properties for persistent storage because the life cycle of state variables mirrors the view life cycle. Instead, use them to manage transient state that only affects the user interface, like the highlight state of a button, filter settings, or the currently selected list item. You might also find this kind of storage convenient while you prototype, before you’re ready to make changes to your app’s data model.

### Manage mutable values as state

If a view needs to store data that it can modify, declare a variable with the [State](State.zh-Hans.md) property wrapper. For example, you can create an `isPlaying` Boolean inside a podcast player view to keep track of when a podcast is running:

```swift
struct PlayerView: View {
    @State private var isPlaying: Bool = false
    
    var body: some View {
        // ...
    }
}
```

Marking the property as state tells the framework to manage the underlying storage. Your view reads and writes the data, found in the state’s [wrappedValue](State/wrappedValue.zh-Hans.md) property, by using the property name. When you change the value, SwiftUI updates the affected parts of the view. For example, you can add a button to the `PlayerView` that toggles the stored value when tapped, and that displays a different image depending on the stored value:

```swift
Button(action: {
    self.isPlaying.toggle()
}) {
    Image(systemName: isPlaying ? "pause.circle" : "play.circle")
}
```

Limit the scope of state variables by declaring them as private. This ensures that the variables remain encapsulated in the view hierarchy that declares them.

### Declare Swift properties to store immutable values

To provide a view with data that the view doesn’t modify, declare a standard Swift property. For example, you can extend the podcast player to have an input structure that contains strings for the episode title and the show name:

```swift
struct PlayerView: View {
    let episode: Episode // The queued episode.
    @State private var isPlaying: Bool = false
    
    var body: some View {
        VStack {
            // Display information about the episode.
            Text(episode.title)
            Text(episode.showTitle)

            Button(action: {
                self.isPlaying.toggle()
            }) {
                Image(systemName: isPlaying ? "pause.circle" : "play.circle")
            }
        }
    }
}
```

While the value of the episode property is a constant for `PlayerView`, it doesn’t need to be constant in this view’s parent view. When the user selects a different episode in the parent, SwiftUI detects the state change and recreates the `PlayerView` with a new input.

### Share access to state with bindings

If a view needs to share control of state with a child view, declare a property in the child with the [Binding](Binding.zh-Hans.md) property wrapper. A binding represents a reference to existing storage, preserving a single source of truth for the underlying data. For example, if you refactor the podcast player view’s button into a child view called `PlayButton`, you can give it a binding to the `isPlaying` property:

```swift
struct PlayButton: View {
    @Binding var isPlaying: Bool
    
    var body: some View {
        Button(action: {
            self.isPlaying.toggle()
        }) {
            Image(systemName: isPlaying ? "pause.circle" : "play.circle")
        }
    }
}
```

As shown above, you read and write the binding’s wrapped value by referring directly to the property, just like state. But unlike a state property, the binding doesn’t have its own storage. Instead, it references a state property stored somewhere else, and provides a two-way connection to that storage.

When you instantiate `PlayButton`, provide a binding to the corresponding state variable declared in the parent view by prefixing it with the dollar sign (`$`):

```swift
struct PlayerView: View {
    var episode: Episode
    @State private var isPlaying: Bool = false
    
    var body: some View {
        VStack {
            Text(episode.title)
            Text(episode.showTitle)
            PlayButton(isPlaying: $isPlaying) // Pass a binding.
        }
    }
}
```

The `$` prefix asks a wrapped property for its [projectedValue](State/projectedValue.zh-Hans.md), which for state is a binding to the underlying storage. Similarly, you can get a binding from a binding using the `$` prefix, allowing you to pass a binding through an arbitrary number of levels of view hierarchy.

You can also get a binding to a scoped value within a state variable. For example, if you declare `episode` as a state variable in the player’s parent view, and the episode structure also contains an `isFavorite` Boolean that you want to control with a toggle, then you can refer to `$episode.isFavorite` to get a binding to the episode’s favorite status:

```swift
struct Podcaster: View {
    @State private var episode = Episode(title: "Some Episode",
                                         showTitle: "Great Show",
                                         isFavorite: false)
    var body: some View {
        VStack {
            Toggle("Favorite", isOn: $episode.isFavorite) // Bind to the Boolean.
            PlayerView(episode: episode)
        }
    }
}
```

### Animate state transitions

When the view state changes, SwiftUI updates affected views right away. If you want to smooth visual transitions, you can tell SwiftUI to animate them by wrapping the state change that triggers them in a call to the [withAnimation(_:_:)](withAnimation.zh-Hans.md) function. For example, you can animate changes controlled by the `isPlaying` Boolean:

```swift
withAnimation(.easeInOut(duration: 1)) {
    self.isPlaying.toggle()
}
```

By changing `isPlaying` inside the animation function’s trailing closure, you tell SwiftUI to animate anything that depends on the wrapped value, like a scale effect on the button’s image:

```swift
Image(systemName: isPlaying ? "pause.circle" : "play.circle")
    .scaleEffect(isPlaying ? 1 : 1.5)
```

SwiftUI transitions the scale effect input over time between the given values of `1` and `1.5`, using the curve and duration that you specify, or reasonable default values if you provide none. On the other hand, the image content isn’t affected by the animation, even though the same Boolean dictates which system image to display. That’s because SwiftUI can’t incrementally transition in a meaningful way between the two strings `pause.circle` and `play.circle`.

You can add animation to a state property, or as in the above example, to a binding. Either way, SwiftUI animates any view changes that happen when the underlying stored value changes. For example, if you add a background color to the `PlayerView` — at a level of view hierarchy above the location of the animation block — SwiftUI animates that as well:

```swift
VStack {
    Text(episode.title)
    Text(episode.showTitle)
    PlayButton(isPlaying: $isPlaying)
}
.background(isPlaying ? Color.green : Color.red) // Transitions with animation.
```

When you want to apply animations to specific views, rather than across all views triggered by a change in state, use the [animation(_:value:)](View/animation___value.zh-Hans.md) view modifier instead.

## Creating and sharing view state

- **State**: A property wrapper type that can read and write a value managed by SwiftUI.
- **Bindable**: A property wrapper type that supports creating bindings to the mutable properties of observable objects.
- **Binding**: A property wrapper type that can read and write a value owned by a source of truth.

