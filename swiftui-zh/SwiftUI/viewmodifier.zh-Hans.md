--- 来源：https://developer.apple.com/documentation/swiftui/viewmodifier
抓取时间：2025-12-02T17:47:15Z

---

# ViewModifier

**Protocol**

您可以将其应用于视图或其他视图修饰符，从而生成原始值的不同版本。

## 声明

```swift
@MainActor @preconcurrency protocol ViewModifier
```

## 概述

如果您想要创建一个可重用的修饰符，并将其应用于任何视图，请采用 [ViewModifier](ViewModifier.zh-Hans.md) 协议。以下示例组合了多个修饰符，创建了一个新修饰符，可用于创建带有圆角矩形边框的蓝色标题文本：

```swift
struct BorderedCaption: ViewModifier {
    func body(content: Content) -> some View {
        content
            .font(.caption2)
            .padding(10)
            .overlay(
                RoundedRectangle(cornerRadius: 15)
                    .stroke(lineWidth: 1)
            )
            .foregroundColor(Color.blue)
    }
}
```

您可以将 [modifier(_:)](View/modifier.zh-Hans.md) 直接应用于视图，但更常见且更符合惯用的方法是使用 [modifier(_:)](View/modifier.zh-Hans.md) 定义 [View](View.zh-Hans.md) 本身的扩展，该扩展包含了视图修饰符：

```swift
extension View {
    func borderedCaption() -> some View {
        modifier(BorderedCaption())
    }
}
```

然后，您可以将带边框的标题应用于任何视图，类似于：

```swift
Image(systemName: "bus")
    .resizable()
    .frame(width:50, height:50)
Text("Downtown Bus")
    .borderedCaption()
```

如果符合此协议的类型在其基本声明中包含该协议，则该类型将继承来自该协议的 `@preconcurrency @MainActor` 隔离：

```swift
struct MyCustomType: Transition {
    // `@preconcurrency @MainActor` isolation by default
}
```

默认情况下，隔离到主要参与者，但这不是必需的。在扩展中声明一致性以选择退出主 Actor 隔离：

```swift
extension MyCustomType: Transition {
    // `nonisolated` by default
}
```

## 创建视图修改器

- **body(content:)**：获取调用者的当前主体。

- **Body**：表示主体的视图类型。

- **ViewModifier.Content**：传递给 `body()` 的内容视图类型。

## 为视图添加动画

- **animation(_:)**：返回修改器的新版本，该版本会将 `animation` 应用于修改器内的所有可动画值。

- **concat(_:)**：返回一个新的修饰符，它是将 `self` 与 `modifier` 连接而成的结果。

## 处理视图点击和手势

- **transaction(_:)**：返回修饰符的新版本，该版本会将事务变更函数 `transform` 应用于修饰符内的所有事务。

## 修改视图

- **配置视图**：通过应用视图修饰符来调整视图的特性。

- **减少视图修饰符的维护**：将您经常重复使用的视图修饰符打包到一个自定义视图修饰符中。

- **modifier(_:)**：将修饰符应用于视图并返回一个新的视图。

- **EmptyModifier**：一个空修饰符（或标识修饰符），用于在开发过程中于编译时切换修饰符。

- **ModifiedContent**：一个应用了修饰符的值。

- **EnvironmentalModifier**：一个修饰符，必须在使用前解析为环境中的具体修饰符。

- **ManipulableModifier**

- **ManipulableResponderModifier**

- **ManipulableTransformBindingModifier**

- **ManipulationGeometryModifier**

- **ManipulationGestureModifier**

- **ManipulationUsingGestureStateModifier**

- **Manipulable**：一个用于各种可操作相关类型的命名空间。

## 继承自

- AnimatableModifier

- EnvironmentalModifier

- GeometryEffect

## 符合的类型

- AccessibilityAttachmentModifier

- EmptyModifier

- LayoutRotationUnaryLayout

- ManipulableModifier

- ManipulableResponderModifier

- ManipulableTransformBindingModifier

- ManipulationGeometryModifier

- ManipulationGestureModifier

- ManipulationUsingGestureStateModifier

- ModifiedContent


---
source: https://developer.apple.com/documentation/swiftui/viewmodifier
crawled: 2025-12-02T17:47:15Z
---

# ViewModifier

**Protocol**

A modifier that you apply to a view or another view modifier, producing a different version of the original value.

## Declaration

```swift
@MainActor @preconcurrency protocol ViewModifier
```

## Overview

Adopt the [ViewModifier](ViewModifier.zh-Hans.md) protocol when you want to create a reusable modifier that you can apply to any view. The example below combines several modifiers to create a new modifier that you can use to create blue caption text surrounded by a rounded rectangle:

```swift
struct BorderedCaption: ViewModifier {
    func body(content: Content) -> some View {
        content
            .font(.caption2)
            .padding(10)
            .overlay(
                RoundedRectangle(cornerRadius: 15)
                    .stroke(lineWidth: 1)
            )
            .foregroundColor(Color.blue)
    }
}
```

You can apply [modifier(_:)](View/modifier.zh-Hans.md) directly to a view, but a more common and idiomatic approach uses [modifier(_:)](View/modifier.zh-Hans.md) to define an extension to [View](View.zh-Hans.md) itself that incorporates the view modifier:

```swift
extension View {
    func borderedCaption() -> some View {
        modifier(BorderedCaption())
    }
}
```

You can then apply the bordered caption to any view, similar to this:

```swift
Image(systemName: "bus")
    .resizable()
    .frame(width:50, height:50)
Text("Downtown Bus")
    .borderedCaption()
```



A type conforming to this protocol inherits `@preconcurrency @MainActor` isolation from the protocol if the conformance is included in the type’s base declaration:

```swift
struct MyCustomType: Transition {
    // `@preconcurrency @MainActor` isolation by default
}
```

Isolation to the main actor is the default, but it’s not required. Declare the conformance in an extension to opt out of main actor isolation:

```swift
extension MyCustomType: Transition {
    // `nonisolated` by default
}
```

## Creating a view modifier

- **body(content:)**: Gets the current body of the caller.
- **Body**: The type of view representing the body.
- **ViewModifier.Content**: The content view type passed to `body()`.

## Adding animations to a view

- **animation(_:)**: Returns a new version of the modifier that will apply `animation` to all animatable values within the modifier.
- **concat(_:)**: Returns a new modifier that is the result of concatenating `self` with `modifier`.

## Handling view taps and gestures

- **transaction(_:)**: Returns a new version of the modifier that will apply the transaction mutation function `transform` to all transactions within the modifier.

## Modifying a view

- **Configuring views**: Adjust the characteristics of a view by applying view modifiers.
- **Reducing view modifier maintenance**: Bundle view modifiers that you regularly reuse into a custom view modifier.
- **modifier(_:)**: Applies a modifier to a view and returns a new view.
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

## Inherited By

- AnimatableModifier
- EnvironmentalModifier
- GeometryEffect

## Conforming Types

- AccessibilityAttachmentModifier
- EmptyModifier
- LayoutRotationUnaryLayout
- ManipulableModifier
- ManipulableResponderModifier
- ManipulableTransformBindingModifier
- ManipulationGeometryModifier
- ManipulationGestureModifier
- ManipulationUsingGestureStateModifier
- ModifiedContent

