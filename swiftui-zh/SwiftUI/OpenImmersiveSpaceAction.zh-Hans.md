---
来源： https://developer.apple.com/documentation/SwiftUI/OpenImmersiveSpaceAction
抓取时间： 2025-12-02T17:21:56Z
---

# 开放式渗透空间行动

**Structure**

呈现沉浸式空间的动作。

## 声明

```swift
@MainActor struct OpenImmersiveSpaceAction
```

## 概览

使用[openImmersiveSpace](EnvironmentValues/openImmersiveSpace.zh-Hans.md) 环境值为给定的[Environment](Environment.zh-Hans.md) 获取此结构的实例。然后调用该实例来显示空间。直接调用实例是因为它定义了 `callAsFunction()` 方法，Swift 在调用实例时会调用这些方法。

在 macOS 上，这可用于打开用 [RemoteImmersiveSpace](RemoteImmersiveSpace.zh-Hans.md) 声明的远程沉浸式空间。当您的应用程序打开远程沉浸式空间时，系统可能会询问用户首选的设备来显示内容。

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

调用是异步的，在显示空格后或出现错误时返回。您可以通过检查调用的返回值（类型为[Result](OpenImmersiveSpaceAction/Result.zh-Hans.md)）来检查错误。例如，如果您已经打开了一个沉浸式空间，则调用会返回错误，因为系统一次只能打开一个空间。

如果您在打开空间时提供了一个值，场景的尾部闭包就会收到与您提供的值的绑定。为获得最佳性能，请为呈现值使用轻量级数据。对于符合[doc://com.apple.documentation/documentation/Swift/Identifiable] 的结构化模型值，值的标识符是一个很好的呈现值，如上面代码中的`planet.ID` 值。

## 调用操作

- **callAsFunction(id:)**：为指定标识符的场景呈现一个沉浸式空间。
- **callAsFunction(id:value:)**：显示您的应用程序为指定标识符定义的沉浸式空间，并处理显示值的类型。
- **callAsFunction(value:)**：显示处理所显示值类型的沉浸式空间。

## 获取结果

- **OpenImmersiveSpaceAction.Result**：尝试打开沉浸式空间的结果。

## 打开沉浸式空间

- **openImmersiveSpace**：呈现沉浸式空间的动作。

## 符合

- 可发送
- 可发送元类型


---
source: https://developer.apple.com/documentation/SwiftUI/OpenImmersiveSpaceAction
crawled: 2025-12-02T17:21:56Z
---

# OpenImmersiveSpaceAction

**Structure**

An action that presents an immersive space.

## Declaration

```swift
@MainActor struct OpenImmersiveSpaceAction
```

## Overview

Use the [openImmersiveSpace](EnvironmentValues/openImmersiveSpace.zh-Hans.md) environment value to get the instance of this structure for a given [Environment](Environment.zh-Hans.md). Then call the instance to present a space. You call the instance directly because it defines `callAsFunction()` methods that Swift calls when you call the instance.

On macOS, this may be used to open a remote immersive space declared with [RemoteImmersiveSpace](RemoteImmersiveSpace.zh-Hans.md). When your app opens a remote immersive space, the system may ask the user for a preferred device with which to display the content.

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

The call is asynchronous and returns after presenting the space or if an error occurs. You can check for errors by inspecting the call’s return value, which is of type [Result](OpenImmersiveSpaceAction/Result.zh-Hans.md). For example, the call returns an error if you already have an immersive space open, because the system enables only one space to be open at a time.

If you provide a value when you open the space, the scene’s trailing closure receives a binding to the value that you provide. For best performance, use lightweight data for the presentation value. For structured model values that conform to [doc://com.apple.documentation/documentation/Swift/Identifiable], the value’s identifier makes a good presentation value, like the `planet.ID` value in the above code.

## Calling the action

- **callAsFunction(id:)**: Presents an immersive space for the scene with the specified identifier.
- **callAsFunction(id:value:)**: Presents the immersive space that your app defines for the specified identifier and that handles the type of the presented value.
- **callAsFunction(value:)**: Presents the immersive space that handles the type of the presented value.

## Getting the result

- **OpenImmersiveSpaceAction.Result**: The outcome of an attempt to open an immersive space.

## Opening an immersive space

- **openImmersiveSpace**: An action that presents an immersive space.

## Conforms To

- Sendable
- SendableMetatype

