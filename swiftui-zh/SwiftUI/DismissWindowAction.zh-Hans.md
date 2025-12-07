---
来源： https://developer.apple.com/documentation/SwiftUI/DismissWindowAction
抓取时间： 2025-12-02T17:21:08Z
---

# DismissWindowAction

**Structure**

用于解除与特定场景关联的窗口的动作。

## 声明

```swift
@MainActor @preconcurrency struct DismissWindowAction
```

## 概览

使用[dismissWindow](EnvironmentValues/dismissWindow.zh-Hans.md) 环境值为给定的[Environment](Environment.zh-Hans.md) 获取此结构的实例。然后调用该实例来解散窗口。我们直接调用该实例是因为它定义了一个 [callAsFunction(id:)](DismissWindowAction/callAsFunction_id.zh-Hans.md) 方法，当我们调用该实例时，Swift 会调用该方法。

例如，您可以定义一个关闭辅助窗口的按钮：

```swift
@main
struct MyApp: App {
    var body: some Scene {
        WindowGroup {
            ContentView()
        }
        #if os(macOS)
        Window("Auxiliary", id: "auxiliary") {
            AuxiliaryContentView()
        }
        #endif
    }
}

struct DismissWindowButton: View {
    @Environment(\.dismissWindow) private var dismissWindow

    var body: some View {
        Button("Close Auxiliary Window") {
            dismissWindow(id: "auxiliary")
        }
    }
}
```

如果该窗口是用[pushWindow](EnvironmentValues/pushWindow.zh-Hans.md) 打开的，则执行该操作后，原来的显示将重新出现。

## 调用操作

- **callAsFunction()**：解除当前窗口。
- **callAsFunction(id:)**：解除与指定标识符关联的窗口。
- **callAsFunction(id:value:)**：删除窗口组定义的窗口，该窗口显示指定的值类型，并与指定的标识符相关联。
- **callAsFunction(value:)**：解散窗口组定义的窗口，该窗口显示指定的值类型。

## 关闭窗口

- **dismissWindow**：存储在视图环境中的窗口关闭操作。
- **dismiss**：解除当前演示的操作。
- **DismissAction**：解散演示文稿的操作。
- **DismissBehavior**：程序性窗口关闭行为。

## 符合

- 可发送
- 可发送元类型


---
source: https://developer.apple.com/documentation/SwiftUI/DismissWindowAction
crawled: 2025-12-02T17:21:08Z
---

# DismissWindowAction

**Structure**

An action that dismisses a window associated to a particular scene.

## Declaration

```swift
@MainActor @preconcurrency struct DismissWindowAction
```

## Overview

Use the [dismissWindow](EnvironmentValues/dismissWindow.zh-Hans.md) environment value to get the instance of this structure for a given [Environment](Environment.zh-Hans.md). Then call the instance to dismiss a window. You call the instance directly because it defines a [callAsFunction(id:)](DismissWindowAction/callAsFunction_id.zh-Hans.md) method that Swift calls when you call the instance.

For example, you can define a button that closes an auxiliary window:

```swift
@main
struct MyApp: App {
    var body: some Scene {
        WindowGroup {
            ContentView()
        }
        #if os(macOS)
        Window("Auxiliary", id: "auxiliary") {
            AuxiliaryContentView()
        }
        #endif
    }
}

struct DismissWindowButton: View {
    @Environment(\.dismissWindow) private var dismissWindow

    var body: some View {
        Button("Close Auxiliary Window") {
            dismissWindow(id: "auxiliary")
        }
    }
}
```

If the window was opened with [pushWindow](EnvironmentValues/pushWindow.zh-Hans.md), the original presenting will reappear when this action is performed.

## Calling the action

- **callAsFunction()**: Dismisses the current window.
- **callAsFunction(id:)**: Dismisses the window that’s associated with the specified identifier.
- **callAsFunction(id:value:)**: Dismisses the window defined by the window group that is presenting the specified value type and that’s associated with the specified identifier.
- **callAsFunction(value:)**: Dismisses the window defined by the window group that is presenting the specified value type.

## Closing windows

- **dismissWindow**: A window dismissal action stored in a view’s environment.
- **dismiss**: An action that dismisses the current presentation.
- **DismissAction**: An action that dismisses a presentation.
- **DismissBehavior**: Programmatic window dismissal behaviors.

## Conforms To

- Sendable
- SendableMetatype

