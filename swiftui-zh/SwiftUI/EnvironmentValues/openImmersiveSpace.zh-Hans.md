---
来源： https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/openImmersiveSpace
抓取时间： 2025-12-02T16:23:01Z
---

# 开放浸入式空间

**实例属性**

呈现沉浸式空间的动作。

## 声明

```swift
var openImmersiveSpace: OpenImmersiveSpaceAction { get }
```

## 讨论

使用此环境值可获取给定[OpenImmersiveSpaceAction](../OpenImmersiveSpaceAction.zh-Hans.md) 结构的[Environment](../Environment.zh-Hans.md) 结构实例。然后调用实例来显示空间。直接调用实例是因为它定义了 `callAsFunction()` 方法，Swift 在调用实例时会调用这些方法。

在 macOS 上，这可用于打开用 [RemoteImmersiveSpace](../RemoteImmersiveSpace.zh-Hans.md) 声明的远程沉浸式空间。当您的应用程序打开远程沉浸式空间时，系统可能会询问用户首选的设备来显示内容。

例如，您可以定义一个按钮来打开沉浸式空间中的一个指定星球：

```swift
@main
struct SolarSystemApp: App {
    var body: some Scene {
        ImmersiveSpace(for: Planet.ID.self) { $planetID in
            // ...
        }
    }
}

struct ShowPlanetButton: View {
    var planet: Planet
    @Environment(\.openImmersiveSpace) private var openImmersiveSpace

    var body: some View {
        Button("Show \(planet.name)") {
            Task {
                await openImmersiveSpace(value: planet.ID)
            }
        }
    }
}
```

您可以通过提供以下信息之一来指明要打开哪个沉浸式空间：

- 通过`id` 参数传递的字符串标识符。
- 一个`value`参数，其类型与您在空间初始化器中指定的类型一致，如上例。
- 既是标识符又是值。这样就可以定义多个空格，这些空格接收相同类型的输入值，并通过字符串标识符加以区分。

调用是异步的，在显示空格后或出现错误时返回。您可以通过检查调用的返回值（类型为[Result](../OpenImmersiveSpaceAction/Result.zh-Hans.md)）来检查错误。例如，如果您已经打开了一个沉浸式空间，则调用会返回错误，因为系统一次只能打开一个空间。

如果您在打开空间时提供了一个值，场景的尾部闭包就会收到与您提供的值的绑定。为获得最佳性能，请为呈现值使用轻量级数据。对于符合[doc://com.apple.documentation/documentation/Swift/Identifiable] 的结构化模型值，值的标识符是一个很好的呈现值，如上面代码中的`planet.ID` 值。

## 打开沉浸式空间

- **OpenImmersiveSpaceAction**：呈现沉浸式空间的动作。


---
source: https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/openImmersiveSpace
crawled: 2025-12-02T16:23:01Z
---

# openImmersiveSpace

**Instance Property**

An action that presents an immersive space.

## Declaration

```swift
var openImmersiveSpace: OpenImmersiveSpaceAction { get }
```

## Discussion

Use this environment value to get the instance of the [OpenImmersiveSpaceAction](../OpenImmersiveSpaceAction.zh-Hans.md) structure for a given [Environment](../Environment.zh-Hans.md). Then call the instance to present a space. You call the instance directly because it defines `callAsFunction()` methods that Swift calls when you call the instance.

On macOS, this may be used to open a remote immersive space declared with [RemoteImmersiveSpace](../RemoteImmersiveSpace.zh-Hans.md). When your app opens a remote immersive space, the system may ask the user for a preferred device with which to display the content.

For example, you can define a button that opens a specified planet in an immersive space:

```swift
@main
struct SolarSystemApp: App {
    var body: some Scene {
        ImmersiveSpace(for: Planet.ID.self) { $planetID in
            // ...
        }
    }
}

struct ShowPlanetButton: View {
    var planet: Planet
    @Environment(\.openImmersiveSpace) private var openImmersiveSpace

    var body: some View {
        Button("Show \(planet.name)") {
            Task {
                await openImmersiveSpace(value: planet.ID)
            }
        }
    }
}
```

You indicate which immersive space to open by providing one of the following:

- A string identifier that you pass through the `id` parameter.
- A `value` parameter that has a type that matches the type that you specify in the space’s initializer, as in the above example.
- Both an identifier and a value. This enables you to define multiple spaces that take input values of the same type and distinguish them by their string identifiers.

The call is asynchronous and returns after presenting the space or if an error occurs. You can check for errors by inspecting the call’s return value, which is of type [Result](../OpenImmersiveSpaceAction/Result.zh-Hans.md). For example, the call returns an error if you already have an immersive space open, because the system enables only one space to be open at a time.

If you provide a value when you open the space, the scene’s trailing closure receives a binding to the value that you provide. For best performance, use lightweight data for the presentation value. For structured model values that conform to [doc://com.apple.documentation/documentation/Swift/Identifiable], the value’s identifier makes a good presentation value, like the `planet.ID` value in the above code.

## Opening an immersive space

- **OpenImmersiveSpaceAction**: An action that presents an immersive space.

