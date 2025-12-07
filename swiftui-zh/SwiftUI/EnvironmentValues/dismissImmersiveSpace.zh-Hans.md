---
来源： https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/dismissImmersiveSpace
抓取时间： 2025-12-02T16:24:22Z
---

# dismissImmersiveSpace

**实例属性**

存储在视图环境中的沉浸式空间解散操作。

## 声明

```swift
var dismissImmersiveSpace: DismissImmersiveSpaceAction { get }
```

## 讨论

使用此环境值可以为给定的 [DismissImmersiveSpaceAction](../DismissImmersiveSpaceAction.zh-Hans.md) 获取一个 [Environment](../Environment.zh-Hans.md) 实例。然后调用该实例来删除空格。我们之所以直接调用该实例，是因为它定义了一个 [callAsFunction()](../DismissImmersiveSpaceAction/callAsFunction.zh-Hans.md) 方法，当我们调用该实例时，Swift 会调用该方法。

在 macOS 上，这可用于解散用 [RemoteImmersiveSpace](../RemoteImmersiveSpace.zh-Hans.md) 声明的远程沉浸式空间。

例如，你可以定义一个按钮来解散沉浸式空间：

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

异步调用在系统完成解散空间后返回。与用于打开空间的[openImmersiveSpace](openImmersiveSpace.zh-Hans.md) 的调用不同--该调用需要一个标识符、一个值或两者来指定要打开的空间--驳回操作不需要参数，因为同一时间只能打开一个沉浸式空间。该调用会关闭当前打开的空间（如果有的话）。

## 关闭沉浸式空间

- **DismissImmersiveSpaceAction**：解除沉浸式空间的操作。


---
source: https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/dismissImmersiveSpace
crawled: 2025-12-02T16:24:22Z
---

# dismissImmersiveSpace

**Instance Property**

An immersive space dismissal action stored in a view’s environment.

## Declaration

```swift
var dismissImmersiveSpace: DismissImmersiveSpaceAction { get }
```

## Discussion

Use this environment value to get a [DismissImmersiveSpaceAction](../DismissImmersiveSpaceAction.zh-Hans.md) instance for a given [Environment](../Environment.zh-Hans.md). Then call the instance to dismiss a space. You call the instance directly because it defines a [callAsFunction()](../DismissImmersiveSpaceAction/callAsFunction.zh-Hans.md) method that Swift calls when you call the instance.

On macOS, this may be used to dismiss a remote immersive space declared with [RemoteImmersiveSpace](../RemoteImmersiveSpace.zh-Hans.md).

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

The asynchronous call returns after the system finishes dismissing the space. Unlike the call to [openImmersiveSpace](openImmersiveSpace.zh-Hans.md) that you use to open the space — which requires an identifier, a value, or both to specify which space to open — the dismiss action requires no parameters because there can be only one immersive space open at a time. The call closes the space that is currently open, if any.

## Closing the immersive space

- **DismissImmersiveSpaceAction**: An action that dismisses an immersive space.

