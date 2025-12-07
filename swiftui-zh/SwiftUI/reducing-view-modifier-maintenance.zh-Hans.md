---
来源： https://developer.apple.com/documentation/swiftui/reducing-view-modifier-maintenance
抓取时间： 2025-12-02T17:47:17Z
---

# 减少视图修改器维护

**Article**

将经常重复使用的视图修改器捆绑到自定义视图修改器中。

### 概览

为创建一致的视图，您可能会在视图中重复使用相同的视图修改器或修改器组。例如，您可能会在整个应用程序中的许多文本实例中应用相同的字体和前景色，这样它们就都匹配了。不幸的是，这可能会带来维护方面的挑战，因为即使是格式上的一个小变化，如不同的字体大小，也需要在代码的许多不同部分进行更改。

为了避免这种开销，可以使用[ViewModifier](ViewModifier.zh-Hans.md) 协议实例将一组修改器收集到一个位置。然后，在[View](View.zh-Hans.md) 协议中扩展一个使用修饰符的方法，使其易于使用和理解。将修改器收集在一起，当您要更改修改器时，只需在一个位置进行更新即可。

### 创建自定义视图修改器

创建自定义修改器时，请根据收集的目的为其命名。例如，如果您在视图中重复应用[caption](font/caption.zh-Hans.md) 字体样式和辅助配色方案来表示辅助样式，则将它们收集在一起，命名为 `CaptionTextFormat`：

```swift
struct CaptionTextFormat: ViewModifier {
    func body(content: Content) -> some View {
        content
            .font(.caption)
            .foregroundColor(.secondary)
    }
}
```

使用[modifier(_:)](View/modifier.zh-Hans.md) 方法应用修饰符。下面的代码将上述示例应用于[Text](Text.zh-Hans.md) 实例：

```swift
Text("Some additional information...")
    .modifier(CaptionTextFormat())
```

### 扩展视图协议，提供流畅的修饰符访问

要方便地访问自定义视图修饰符，可扩展[View](View.zh-Hans.md) 协议，使其包含一个可应用修饰符的函数：

```swift
extension View {
    func captionTextFormat() -> some View {
        modifier(CaptionTextFormat())
    }
}
```

通过包含此扩展名将修改器应用于文本视图：

```swift
Text("Some additional information...")
    .captionTextFormat()
```

## 修改视图

- 配置视图**：通过应用视图修改器来调整视图的特性。
- **modifier(_:)**：向视图应用修改器并返回新视图。
- **ViewModifier**：将修改器应用到视图或另一个视图修改器，生成原始值的不同版本。
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
source: https://developer.apple.com/documentation/swiftui/reducing-view-modifier-maintenance
crawled: 2025-12-02T17:47:17Z
---

# Reducing view modifier maintenance

**Article**

Bundle view modifiers that you regularly reuse into a custom view modifier.

## Overview

To create consistent views, you might reuse the same view modifier or group of modifiers repeatedly across your views. For example, you might apply the same font and foreground color to many text instances throughout your app, so they all match. Unfortunately, this can lead to maintenance challenges, because even a small change in format, like a different font size, requires changes in many different parts of your code.

To avoid this overhead, collect a set of modifiers into a single location using an instance of the [ViewModifier](ViewModifier.zh-Hans.md) protocol. Then, extend the [View](View.zh-Hans.md) protocol with a method that uses your modifier, making it easy to use and understand. Collecting the modifiers together provides a single location to update when you want to change them.

### Create a custom view modifier

When you create your custom modifier, name it to reflect the purpose of the collection. For example, if you repeatedly apply the [caption](font/caption.zh-Hans.md) font style and a secondary color scheme to views to represent a secondary styling, collect them together as `CaptionTextFormat`:

```swift
struct CaptionTextFormat: ViewModifier {
    func body(content: Content) -> some View {
        content
            .font(.caption)
            .foregroundColor(.secondary)
    }
}
```

Apply your modifier using the [modifier(_:)](View/modifier.zh-Hans.md) method. The following code applies the above example to a [Text](Text.zh-Hans.md) instance:

```swift
Text("Some additional information...")
    .modifier(CaptionTextFormat())
```

### Extend the view protocol to provide fluent modifier access

To make your custom view modifier conveniently accessible, extend the [View](View.zh-Hans.md) protocol with a function that applies your modifier:

```swift
extension View {
    func captionTextFormat() -> some View {
        modifier(CaptionTextFormat())
    }
}
```

Apply the modifier to a text view by including this extension:

```swift
Text("Some additional information...")
    .captionTextFormat()
```

## Modifying a view

- **Configuring views**: Adjust the characteristics of a view by applying view modifiers.
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

