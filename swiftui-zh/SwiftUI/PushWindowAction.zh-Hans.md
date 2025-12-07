---
来源： https://developer.apple.com/documentation/SwiftUI/PushWindowAction
抓取时间： 2025-12-02T17:21:07Z
---

# PushWindowAction

**Structure**

打开所请求窗口的操作，以替代该操作被调用的窗口。

### 声明

```swift
@MainActor struct PushWindowAction
```

## 概览

调用此操作的场景将被背景化。请求的场景将与背景场景居中对齐。请求的场景的默认大小与背景场景的大小一致。关闭请求的窗口将导致背景场景重新出现。

从推送的窗口调用[dismissWindow](EnvironmentValues/dismissWindow.zh-Hans.md) 解除推送的窗口并显示背景窗口。

不允许从推送窗口调用此操作。

使用[pushWindow](EnvironmentValues/pushWindow.zh-Hans.md) 环境值获取给定[Environment](Environment.zh-Hans.md) 的此结构体实例。然后调用该实例来推送窗口。我们直接调用该实例，因为它定义了一个 [callAsFunction(id:)](PushWindowAction/callAsFunction_id.zh-Hans.md) 方法，当我们调用该实例时，Swift 会调用该方法。

例如，您可以定义一个按钮，从编辑器窗口推送视频预览：

```swift
@main
struct VideoEditor: App {
    var body: some Scene {
        WindowGroup(id: "editor") {
            EditorView()
        }

        WindowGroup(id: "viewer") {
            VideoView()
        }
    }
}

struct EditorView: View {
    @Environment(\.pushWindow) private var pushWindow

    var body: some View {
        Button("Play", systemImage: "play.fill") {
            pushWindow(id: "viewer")
        }
    }
}
```

您可以通过提供以下选项之一来指定要推送的场景：

- 通过`id` 参数传递的字符串标识符，如上例。
- 一个`value`参数，其类型与您在场景初始化器中指定的类型一致。
- 既是标识符又是值。这样就可以定义多个窗口组，这些窗口组接受相同类型的输入值，如[doc://com.apple.documentation/documentation/Foundation/UUID]。

使用第一个选项，可以在应用程序中将具有匹配标识符的[WindowGroup](WindowGroup.zh-Hans.md) 或[Window](Window.zh-Hans.md) 场景作为目标。对于[WindowGroup](WindowGroup.zh-Hans.md)，系统会为该组创建一个新窗口。如果窗口组显示数据，系统会向窗口的根视图提供默认值或`nil`。如果目标场景是[Window](Window.zh-Hans.md)，系统会将它排在前面。

使用其他两个选项将[WindowGroup](WindowGroup.zh-Hans.md) 作为目标，并提供一个值来呈现。如果界面中已经有一个窗口正在显示指定的值，系统就会将该窗口调到前面。否则，系统将创建一个新窗口，并将绑定传递给指定值。

### 实例方法

- **callAsFunction(id:)**：推送与指定标识符相关联的窗口。
- **callAsFunction(id:value:)**：推送窗口组定义的窗口，该窗口显示指定的值类型，并与指定的标识符相关联。
- **callAsFunction(value:)**：推送窗口组定义的窗口，该窗口显示指定值的类型。

## 打开窗口

- 呈现窗口和空间**：打开和关闭构成应用程序界面的场景。
- **supportsMultipleWindows**：布尔值，表示当前平台是否支持打开多个窗口。
- **openWindow**：存储在视图环境中的窗口演示操作。
- **OpenWindowAction**：显示窗口的操作。

## 符合

- 可发送
- 可发送元类型


---
source: https://developer.apple.com/documentation/SwiftUI/PushWindowAction
crawled: 2025-12-02T17:21:07Z
---

# PushWindowAction

**Structure**

An action that opens the requested window in place of the window the action is called from.

## Declaration

```swift
@MainActor struct PushWindowAction
```

## Overview

The scene this action is called from will be backgrounded. The requested scene will be center-aligned with the backgrounded scene. The requested scene will have a default size that matches the size of the backgrounded scene. Closing the requested window will result in the backgrounded scene reappearing.

Call [dismissWindow](EnvironmentValues/dismissWindow.zh-Hans.md) from the pushed window to dismiss the pushed window and show the backgrounded window.

Calling this action from a pushed window is not allowed.

Use the [pushWindow](EnvironmentValues/pushWindow.zh-Hans.md) environment value to get the instance of this structure for a given [Environment](Environment.zh-Hans.md). Then call the instance to push a window. You call the instance directly because it defines a [callAsFunction(id:)](PushWindowAction/callAsFunction_id.zh-Hans.md) method that Swift calls when you call the instance.

For example, you can define a button that pushes a video preview from an editor window:

```swift
@main
struct VideoEditor: App {
    var body: some Scene {
        WindowGroup(id: "editor") {
            EditorView()
        }

        WindowGroup(id: "viewer") {
            VideoView()
        }
    }
}

struct EditorView: View {
    @Environment(\.pushWindow) private var pushWindow

    var body: some View {
        Button("Play", systemImage: "play.fill") {
            pushWindow(id: "viewer")
        }
    }
}
```

You indicate which scene to push by providing one of the following:

- A string identifier that you pass through the `id` parameter, as in the above example.
- A `value` parameter that has a type that matches the type that you specify in the scene’s initializer.
- Both an identifier and a value. This enables you to define multiple window groups that take input values of the same type, like a [doc://com.apple.documentation/documentation/Foundation/UUID].

Use the first option to target either a [WindowGroup](WindowGroup.zh-Hans.md) or a [Window](Window.zh-Hans.md) scene in your app that has a matching identifier. For a [WindowGroup](WindowGroup.zh-Hans.md), the system creates a new window for the group. If the window group presents data, the system provides the default value or `nil` to the window’s root view. If the targeted scene is a [Window](Window.zh-Hans.md), the system orders it to the front.

Use the other two options to target a [WindowGroup](WindowGroup.zh-Hans.md) and provide a value to present. If the interface already has a window from the group that is presenting the specified value, the system brings the window to the front. Otherwise, the system creates a new window and passes a binding to the specified value.

## Instance Methods

- **callAsFunction(id:)**: Pushes a window that is associated with the specified identifier.
- **callAsFunction(id:value:)**: Pushes a window defined by the window group that presents the specified value type and that is associated with the specified identifier.
- **callAsFunction(value:)**: Pushes a window defined by a window group that presents the type of the specified value.

## Opening windows

- **Presenting windows and spaces**: Open and close the scenes that make up your app’s interface.
- **supportsMultipleWindows**: A Boolean value that indicates whether the current platform supports opening multiple windows.
- **openWindow**: A window presentation action stored in a view’s environment.
- **OpenWindowAction**: An action that presents a window.

## Conforms To

- Sendable
- SendableMetatype

