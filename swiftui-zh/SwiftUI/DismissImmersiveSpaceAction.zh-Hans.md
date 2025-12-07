--- 来源：https://developer.apple.com/documentation/SwiftUI/DismissImmersiveSpaceAction
抓取时间：2025-12-02T17:21:57Z

---

# DismissImmersiveSpaceAction

**Structure**

用于关闭沉浸式空间的操作。

## 声明

```swift
@MainActor struct DismissImmersiveSpaceAction
```

## 概述

使用 [dismissImmersiveSpace](EnvironmentValues/dismissImmersiveSpace.zh-Hans.md) 环境变量值，为给定的 [Environment](Environment.zh-Hans.md) 获取此类型的实例。然后调用该实例来关闭空间。之所以直接调用实例，是因为它定义了一个 [callAsFunction()](DismissImmersiveSpaceAction/callAsFunction.zh-Hans.md) 方法，Swift 会在调用实例时调用该方法。

在 macOS 上，此方法可用于关闭使用 [RemoteImmersiveSpace](RemoteImmersiveSpace.zh-Hans.md) 声明的远程沉浸式空间。

例如，您可以定义一个用于关闭沉浸式空间的按钮：

```swift
@main
struct MyApp: App {
    var body: some Scene {
        WindowGroup {
            DismissImmersiveSpaceButton()
        }
        ImmersiveSpace(id: "solarSystem") {
            SolarSystemView()
        }
    }
}

struct DismissImmersiveSpaceButton: View {
    @Environment(\.dismissImmersiveSpace) private var dismissImmersiveSpace

    var body: some View {
        Button("Dismiss") {
            Task {
                await dismissImmersiveSpace()
            }
        }
    }
}
```

异步调用会在系统完成空间关闭后返回。与您用于打开空间的 [openImmersiveSpace](EnvironmentValues/openImmersiveSpace.zh-Hans.md) 调用（需要标识符、值或两者都需要来指定要打开的空间）不同，关闭操作不需要任何参数，因为一次只能打开一个沉浸式空间。该调用会关闭当前打开的空间（如果有）。

## 调用操作

- **callAsFunction()**：关闭当前打开的沉浸式空间。

## 关闭沉浸式空间

- **dismissImmersiveSpace**：存储在视图环境中的沉浸式空间关闭操作。

## 符合以下规范

- Sendable

- SendableMetatype


---
source: https://developer.apple.com/documentation/SwiftUI/DismissImmersiveSpaceAction
crawled: 2025-12-02T17:21:57Z
---

# DismissImmersiveSpaceAction

**Structure**

An action that dismisses an immersive space.

## Declaration

```swift
@MainActor struct DismissImmersiveSpaceAction
```

## Overview

Use the [dismissImmersiveSpace](EnvironmentValues/dismissImmersiveSpace.zh-Hans.md) environment value to get an instance of this type for a given [Environment](Environment.zh-Hans.md). Then call the instance to dismiss a space. You call the instance directly because it defines a [callAsFunction()](DismissImmersiveSpaceAction/callAsFunction.zh-Hans.md) method that Swift calls when you call the instance.

On macOS, this may be used to dismiss a remote immersive space declared with [RemoteImmersiveSpace](RemoteImmersiveSpace.zh-Hans.md).

For example, you can define a button that dismisses an immersive space:

```swift
@main
struct MyApp: App {
    var body: some Scene {
        WindowGroup {
            DismissImmersiveSpaceButton()
        }
        ImmersiveSpace(id: "solarSystem") {
            SolarSystemView()
        }
    }
}

struct DismissImmersiveSpaceButton: View {
    @Environment(\.dismissImmersiveSpace) private var dismissImmersiveSpace

    var body: some View {
        Button("Dismiss") {
            Task {
                await dismissImmersiveSpace()
            }
        }
    }
}
```

The asynchronous call returns after the system finishes dismissing the space. Unlike the call to [openImmersiveSpace](EnvironmentValues/openImmersiveSpace.zh-Hans.md) that you use to open the space — which requires an identifier, a value, or both to specify which space to open — the dismiss action requires no parameters because there can be only one immersive space open at a time. The call closes the space that is currently open, if any.

## Calling the action

- **callAsFunction()**: Dismisses the currently opened immersive space.

## Closing the immersive space

- **dismissImmersiveSpace**: An immersive space dismissal action stored in a view’s environment.

## Conforms To

- Sendable
- SendableMetatype

