---
来源： https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/dismissWindow
抓取时间： 2025-12-02T16:24:18Z
---

# dismissWindow

**实例属性**

存储在视图环境中的窗口解散操作。

## 声明

```swift
var dismissWindow: DismissWindowAction { get }
```

## 讨论

使用 `dismissWindow` 环境值为给定的 [DismissWindowAction](../DismissWindowAction.zh-Hans.md) 实例获取 [Environment](../Environment.zh-Hans.md)。然后调用该实例来解散窗口。您直接调用实例是因为它定义了一个 [callAsFunction(id:)](../DismissWindowAction/callAsFunction_id.zh-Hans.md) 方法，当您调用实例时，Swift 会调用该方法。

例如，您可以定义一个按钮来解散一个辅助窗口：

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

如果该窗口是用[pushWindow](pushWindow.zh-Hans.md)打开的，则执行该操作后，显示窗口将重新出现。

## 关闭窗口

- **DismissWindowAction**：用于关闭与特定场景相关联的窗口的操作。
- **dismiss**：解散当前演示文稿的操作。
- **DismissAction**：解散演示文稿的操作。
- **DismissBehavior**：程序性窗口关闭行为。


---
source: https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/dismissWindow
crawled: 2025-12-02T16:24:18Z
---

# dismissWindow

**Instance Property**

A window dismissal action stored in a view’s environment.

## Declaration

```swift
var dismissWindow: DismissWindowAction { get }
```

## Discussion

Use the `dismissWindow` environment value to get an [DismissWindowAction](../DismissWindowAction.zh-Hans.md) instance for a given [Environment](../Environment.zh-Hans.md). Then call the instance to dismiss a window. You call the instance directly because it defines a [callAsFunction(id:)](../DismissWindowAction/callAsFunction_id.zh-Hans.md) method that Swift calls when you call the instance.

For example, you can define a button that dismisses an auxiliary window:

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

If the window was opened with [pushWindow](pushWindow.zh-Hans.md), the presenting window will reappear when this action is performed.

## Closing windows

- **DismissWindowAction**: An action that dismisses a window associated to a particular scene.
- **dismiss**: An action that dismisses the current presentation.
- **DismissAction**: An action that dismisses a presentation.
- **DismissBehavior**: Programmatic window dismissal behaviors.

