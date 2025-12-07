---
来源： https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/pushWindow
抓取时间： 2025-12-03T06:07:11Z
---

# pushWindow

**实例属性**

存储在视图环境中的窗口展示操作。

## 声明

```swift
var pushWindow: PushWindowAction { get }
```

## 讨论

此操作将打开所请求的窗口，以替代调用此操作的窗口。调用此操作的场景将被背景化。请求的场景将与背景场景居中对齐。请求的场景的默认大小与背景场景的大小一致。关闭请求的窗口将导致背景场景重新出现。

从推送的窗口调用[dismissWindow](dismissWindow.zh-Hans.md) 解除推送的窗口并显示背景窗口。

不允许从推送窗口调用此操作。

或者，使用 [openWindow](openWindow.zh-Hans.md) 打开一个与调用该操作的窗口分开的窗口。

使用`pushWindow` 环境值为给定的[PushWindowAction](../PushWindowAction.zh-Hans.md) 实例获取[Environment](../Environment.zh-Hans.md)。然后调用该实例来推送窗口。您直接调用实例是因为它定义了一个 [callAsFunction(id:)](../PushWindowAction/callAsFunction_id.zh-Hans.md) 方法，当您调用实例时，Swift 会调用该方法。

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
- 既是标识符又是值。这样，您就可以定义多个窗口组，这些窗口组接受与[doc://com.apple.documentation/documentation/Foundation/UUID]类型相同的输入值。

使用第一个选项可在应用程序中针对具有匹配标识符的[WindowGroup](../WindowGroup.zh-Hans.md) 或[Window](../Window.zh-Hans.md) 场景。对于[WindowGroup](../WindowGroup.zh-Hans.md)，系统会为该组创建一个新窗口。如果窗口组显示数据，系统会向窗口的根视图提供默认值或`nil`。如果目标场景是`Window`，系统会将它排在前面。

使用其他两个选项以[WindowGroup](../WindowGroup.zh-Hans.md) 为目标，并提供一个值来呈现。如果界面上已经有一个正在显示指定值的窗口，系统就会将该窗口放到前面。否则，系统将创建一个新窗口，并将绑定传递给指定值。

### 操作

- **dismiss**：解除当前演示的操作。
- **dismissSearch**：结束当前搜索交互的操作。
- **dismissWindow**：存储在视图环境中的窗口关闭操作。
- **openImmersiveSpace**：呈现沉浸式空间的操作。
- **dismissImmersiveSpace**：存储在视图环境中的沉浸式空间取消动作。
- **newDocument**：环境中显示新文档的操作。
- **openDocument**：环境中显示现有文档的操作。
- **openURL**：打开 URL 的操作。
- **openWindow**：存储在视图环境中的窗口演示操作。
- **purchase**：启动应用程序内购买的操作。
- **refresh**：存储在视图环境中的刷新操作。
- **rename**：激活标准重命名交互的操作。
- **resetFocus**：请求焦点系统重新评估默认焦点的操作。
- **openSettings**：存储在视图环境中的设置演示操作。


---
source: https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/pushWindow
crawled: 2025-12-03T06:07:11Z
---

# pushWindow

**Instance Property**

A window presentation action stored in a view’s environment.

## Declaration

```swift
var pushWindow: PushWindowAction { get }
```

## Discussion

This action opens the requested window in place of the window the action is called from. The scene this action is called from will be backgrounded. The requested scene will be center-aligned with the backgrounded scene. The requested scene will have a default size that matches the size of the backgrounded scene. Closing the requested window will result in the backgrounded scene reappearing.

Call [dismissWindow](dismissWindow.zh-Hans.md) from the pushed window to dismiss the pushed window and show the backgrounded window.

Calling this action from a pushed window is not allowed.

Alternatively, use [openWindow](openWindow.zh-Hans.md) to open a window separate from the window the action is called from.

Use the `pushWindow` environment value to get an [PushWindowAction](../PushWindowAction.zh-Hans.md) instance for a given [Environment](../Environment.zh-Hans.md). Then call the instance to push a window. You call the instance directly because it defines a [callAsFunction(id:)](../PushWindowAction/callAsFunction_id.zh-Hans.md) method that Swift calls when you call the instance.

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
- Both an identifier and a value. This enables you to define multiple window groups that take input values of the same type like a [doc://com.apple.documentation/documentation/Foundation/UUID].

Use the first option to target either a [WindowGroup](../WindowGroup.zh-Hans.md) or a [Window](../Window.zh-Hans.md) scene in your app that has a matching identifier. For a [WindowGroup](../WindowGroup.zh-Hans.md), the system creates a new window for the group. If the window group presents data, the system provides the default value or `nil` to the window’s root view. If the targeted scene is a `Window`, the system orders it to the front.

Use the other two options to target a [WindowGroup](../WindowGroup.zh-Hans.md) and provide a value to present. If the interface already has a window from the group that is presenting the specified value, the system brings the window to the front. Otherwise, the system creates a new window and passes a binding to the specified value.

## Actions

- **dismiss**: An action that dismisses the current presentation.
- **dismissSearch**: An action that ends the current search interaction.
- **dismissWindow**: A window dismissal action stored in a view’s environment.
- **openImmersiveSpace**: An action that presents an immersive space.
- **dismissImmersiveSpace**: An immersive space dismissal action stored in a view’s environment.
- **newDocument**: An action in the environment that presents a new document.
- **openDocument**: An action in the environment that presents an existing document.
- **openURL**: An action that opens a URL.
- **openWindow**: A window presentation action stored in a view’s environment.
- **purchase**: An action that starts an in-app purchase.
- **refresh**: A refresh action stored in a view’s environment.
- **rename**: An action that activates the standard rename interaction.
- **resetFocus**: An action that requests the focus system to reevaluate default focus.
- **openSettings**: A Settings presentation action stored in a view’s environment.

