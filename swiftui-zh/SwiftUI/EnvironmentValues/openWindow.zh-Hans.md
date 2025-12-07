---
来源： https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/openWindow
抓取时间： 2025-12-02T16:23:18Z
---

# 打开窗口

**实例属性**

存储在视图环境中的窗口展示操作。

## 声明

```swift
var openWindow: OpenWindowAction { get }
```

## 讨论

使用`openWindow` 环境值为给定的[OpenWindowAction](../OpenWindowAction.zh-Hans.md) 获取一个[Environment](../Environment.zh-Hans.md) 实例。然后调用该实例打开一个窗口。我们直接调用实例是因为它定义了一个 [callAsFunction(id:)](../OpenWindowAction/callAsFunction_id.zh-Hans.md) 方法，当我们调用实例时，Swift 会调用该方法。

例如，您可以定义一个按钮来打开一个新的邮件查看器窗口：

```swift
@main
struct Mail: App {
    var body: some Scene {
        WindowGroup(id: "mail-viewer") {
            MailViewer()
        }
    }
}

struct NewViewerButton: View {
    @Environment(\.openWindow) private var openWindow

    var body: some View {
        Button("Open new mail viewer") {
            openWindow(id: "mail-viewer")
        }
    }
}
```

您可以通过提供以下选项之一来指明要打开的场景：

- 通过`id` 参数传递的字符串标识符，如上例。
- 一个`value`参数，其类型与您在场景初始化器中指定的类型一致。
- 既是标识符又是值。这样，您就可以定义多个窗口组，这些窗口组接受与[doc://com.apple.documentation/documentation/Foundation/UUID]类型相同的输入值。

使用第一个选项可在应用程序中针对具有匹配标识符的[WindowGroup](../WindowGroup.zh-Hans.md) 或[Window](../Window.zh-Hans.md) 场景。对于`WindowGroup`，系统会为该组创建一个新窗口。如果窗口组显示数据，系统会向窗口的根视图提供默认值或`nil`。如果目标场景是`Window`，系统会将它排在前面。

使用其他两个选项将`WindowGroup` 作为目标，并提供一个值来呈现。如果界面中已经有一个窗口正在显示指定的值，系统就会将该窗口调到前面。否则，系统将创建一个新窗口，并将绑定传递给指定值。

## 打开窗口

- 呈现窗口和空间**：打开和关闭构成应用程序界面的场景。
- **supportsMultipleWindows**：布尔值，表示当前平台是否支持打开多个窗口。
- **OpenWindowAction**：显示窗口的操作。
- **PushWindowAction**：打开所请求窗口的操作，以代替该操作被调用的窗口。


---
source: https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/openWindow
crawled: 2025-12-02T16:23:18Z
---

# openWindow

**Instance Property**

A window presentation action stored in a view’s environment.

## Declaration

```swift
var openWindow: OpenWindowAction { get }
```

## Discussion

Use the `openWindow` environment value to get an [OpenWindowAction](../OpenWindowAction.zh-Hans.md) instance for a given [Environment](../Environment.zh-Hans.md). Then call the instance to open a window. You call the instance directly because it defines a [callAsFunction(id:)](../OpenWindowAction/callAsFunction_id.zh-Hans.md) method that Swift calls when you call the instance.

For example, you can define a button that opens a new mail viewer window:

```swift
@main
struct Mail: App {
    var body: some Scene {
        WindowGroup(id: "mail-viewer") {
            MailViewer()
        }
    }
}

struct NewViewerButton: View {
    @Environment(\.openWindow) private var openWindow

    var body: some View {
        Button("Open new mail viewer") {
            openWindow(id: "mail-viewer")
        }
    }
}
```

You indicate which scene to open by providing one of the following:

- A string identifier that you pass through the `id` parameter, as in the above example.
- A `value` parameter that has a type that matches the type that you specify in the scene’s initializer.
- Both an identifier and a value. This enables you to define multiple window groups that take input values of the same type like a [doc://com.apple.documentation/documentation/Foundation/UUID].

Use the first option to target either a [WindowGroup](../WindowGroup.zh-Hans.md) or a [Window](../Window.zh-Hans.md) scene in your app that has a matching identifier. For a `WindowGroup`, the system creates a new window for the group. If the window group presents data, the system provides the default value or `nil` to the window’s root view. If the targeted scene is a `Window`, the system orders it to the front.

Use the other two options to target a `WindowGroup` and provide a value to present. If the interface already has a window from the group that’s presenting the specified value, the system brings the window to the front. Otherwise, the system creates a new window and passes a binding to the specified value.

## Opening windows

- **Presenting windows and spaces**: Open and close the scenes that make up your app’s interface.
- **supportsMultipleWindows**: A Boolean value that indicates whether the current platform supports opening multiple windows.
- **OpenWindowAction**: An action that presents a window.
- **PushWindowAction**: An action that opens the requested window in place of the window the action is called from.

