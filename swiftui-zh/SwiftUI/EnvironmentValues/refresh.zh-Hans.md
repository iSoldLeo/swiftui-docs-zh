---
来源： https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/refresh
抓取时间： 2025-12-02T17:39:47Z
---

# 刷新

**实例属性**

存储在视图环境中的刷新操作。

## 声明

```swift
var refresh: RefreshAction? { get }
```

## 讨论

当该环境值包含[RefreshAction](../RefreshAction.zh-Hans.md) 结构的实例时，相应[Environment](../Environment.zh-Hans.md) 中的某些内置视图就会开始提供刷新功能。它们会将实例的处理程序应用于用户启动的任何刷新操作。默认情况下，环境值为 `nil`，但您可以使用 [refreshable(action:)](../View/refreshable_action.zh-Hans.md)修饰符来创建和存储使用您指定的处理程序的新刷新操作：

```swift
List(mailbox.conversations) { conversation in
    ConversationCell(conversation)
}
.refreshable {
    await mailbox.fetch()
}
```

在 iOS 和 iPadOS 上，上例中的[List](../List.zh-Hans.md) 提供了一个拉动刷新手势，因为它能检测到刷新操作。当用户向下拖动列表并松开时，列表会调用动作的处理程序。由于 SwiftUI 将处理程序声明为异步，因此可以安全地进行长时间运行的异步调用，例如获取网络数据。

### 刷新自定义视图

您还可以在自定义视图中提供刷新功能。读取`refresh`环境值，以获取给定[RefreshAction](../RefreshAction.zh-Hans.md)实例。如果您发现了一个非`nil` 值，请更改视图的外观或行为，以便向用户提供刷新，并调用该实例来进行刷新。您可以直接调用刷新实例，因为它定义了一个 [callAsFunction()](../RefreshAction/callAsFunction.zh-Hans.md) 方法，当您调用实例时，Swift 会调用该方法：

```swift
struct RefreshableView: View {
    @Environment(\.refresh) private var refresh

    var body: some View {
        Button("Refresh") {
            Task {
                await refresh?()
            }
        }
        .disabled(refresh == nil)
    }
}
```

请确保异步调用处理程序，在其前面加上 `await`。由于调用是异步的，因此可以利用其生命周期向用户显示进度。例如，您可以在调用处理程序前显示一个不确定的[ProgressView](../ProgressView.zh-Hans.md)，并在处理程序完成后隐藏它。

如果您的代码尚未处于异步上下文中，请创建一个 [doc://com.apple.documentation/documentation/Swift/Task]，让方法在其中运行。如果这样做，请考虑为用户添加取消任务的方法。更多信息，请参阅 *The Swift Programming Language* 中的 [https://docs.swift.org/swift-book/LanguageGuide/Concurrency.html]。

## 刷新列表内容

- **refreshable(action:)**：将此视图标记为可刷新。
- **RefreshAction**：启动刷新操作的操作。


---
source: https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/refresh
crawled: 2025-12-02T17:39:47Z
---

# refresh

**Instance Property**

A refresh action stored in a view’s environment.

## Declaration

```swift
var refresh: RefreshAction? { get }
```

## Discussion

When this environment value contains an instance of the [RefreshAction](../RefreshAction.zh-Hans.md) structure, certain built-in views in the corresponding [Environment](../Environment.zh-Hans.md) begin offering a refresh capability. They apply the instance’s handler to any refresh operation that the user initiates. By default, the environment value is `nil`, but you can use the [refreshable(action:)](../View/refreshable_action.zh-Hans.md) modifier to create and store a new refresh action that uses the handler that you specify:

```swift
List(mailbox.conversations) { conversation in
    ConversationCell(conversation)
}
.refreshable {
    await mailbox.fetch()
}
```

On iOS and iPadOS, the [List](../List.zh-Hans.md) in the example above offers a pull to refresh gesture because it detects the refresh action. When the user drags the list down and releases, the list calls the action’s handler. Because SwiftUI declares the handler as asynchronous, it can safely make long-running asynchronous calls, like fetching network data.

### Refreshing custom views

You can also offer refresh capability in your custom views. Read the `refresh` environment value to get the [RefreshAction](../RefreshAction.zh-Hans.md) instance for a given [Environment](../Environment.zh-Hans.md). If you find a non-`nil` value, change your view’s appearance or behavior to offer the refresh to the user, and call the instance to conduct the refresh. You can call the refresh instance directly because it defines a [callAsFunction()](../RefreshAction/callAsFunction.zh-Hans.md) method that Swift calls when you call the instance:

```swift
struct RefreshableView: View {
    @Environment(\.refresh) private var refresh

    var body: some View {
        Button("Refresh") {
            Task {
                await refresh?()
            }
        }
        .disabled(refresh == nil)
    }
}
```

Be sure to call the handler asynchronously by preceding it with `await`. Because the call is asynchronous, you can use its lifetime to indicate progress to the user. For example, you can reveal an indeterminate [ProgressView](../ProgressView.zh-Hans.md) before calling the handler, and hide it when the handler completes.

If your code isn’t already in an asynchronous context, create a [doc://com.apple.documentation/documentation/Swift/Task] for the method to run in. If you do this, consider adding a way for the user to cancel the task. For more information, see [https://docs.swift.org/swift-book/LanguageGuide/Concurrency.html] in *The Swift Programming Language*.

## Refreshing a list’s content

- **refreshable(action:)**: Marks this view as refreshable.
- **RefreshAction**: An action that initiates a refresh operation.

