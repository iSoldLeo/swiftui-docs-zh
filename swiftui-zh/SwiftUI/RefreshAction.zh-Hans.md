--- 来源：https://developer.apple.com/documentation/SwiftUI/RefreshAction
抓取时间：2025-12-02T17:39:48Z

---

# RefreshAction

**Structure**

一个用于启动刷新操作的操作。

## 声明

```swift
struct RefreshAction
```

## 概述

当 [refresh](EnvironmentValues/refresh.zh-Hans.md) 环境变量包含此结构的实例时，对应的 [Environment](Environment.zh-Hans.md) 中的某些内置视图将开始提供刷新功能。它们会将该实例的处理程序应用于用户启动的任何刷新操作。默认情况下，环境变量值为 `nil`，但您可以使用 [refreshable(action:)](View/refreshable_action.zh-Hans.md) 修饰符来创建并存储一个新的刷新操作，该操作使用您指定的处理程序：

```swift
List(mailbox.conversations) { conversation in
    ConversationCell(conversation)
}
.refreshable {
    await mailbox.fetch()
}
```

在 iOS 和 iPadOS 上，上述示例中的 [List](List.zh-Hans.md) 提供下拉刷新手势，因为它能够检测到刷新操作。当用户向下拖动列表并松开时，列表会调用该操作的处理程序。由于 SwiftUI 将处理程序声明为异步，因此它可以安全地进行长时间运行的异步调用，例如获取网络数据。

### 刷新自定义视图

您还可以在自定义视图中提供刷新功能。读取 [refresh](EnvironmentValues/refresh.zh-Hans.md) 环境变量值，即可获取给定 [Environment](Environment.zh-Hans.md) 对应的 `RefreshAction` 实例。如果找到非 `nil` 值，请更改视图的外观或行为，以便向用户提供刷新选项，并调用实例来执行刷新。您可以直接调用刷新实例，因为它定义了一个 [callAsFunction()](RefreshAction/callAsFunction.zh-Hans.md) 方法，Swift 会在您调用该实例时调用该方法：

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

请务必通过在处理程序前加上 `await` 来异步调用它。由于调用是异步的，您可以使用其生命周期向用户指示进度。例如，您可以在调用处理程序之前显示一个不确定的 [ProgressView](ProgressView.zh-Hans.md)，并在处理程序完成后将其隐藏。

如果您的代码尚未处于异步上下文中，请创建一个 [doc://com.apple.documentation/documentation/Swift/Task] 来运行该方法。如果这样做，请考虑添加允许用户取消任务的方法。更多信息，请参阅《Swift 程序设计语言》中的 [https://docs.swift.org/swift-book/LanguageGuide/Concurrency.html]。

## 调用操作

- **callAsFunction()**：发起刷新操作。

## 刷新列表内容

- **refreshable(action:)**：将此视图标记为可刷新。

- **refresh**：存储在视图环境中的刷新操作。

## 符合以下协议：

- Sendable

- SendableMetatype


---
source: https://developer.apple.com/documentation/SwiftUI/RefreshAction
crawled: 2025-12-02T17:39:48Z
---

# RefreshAction

**Structure**

An action that initiates a refresh operation.

## Declaration

```swift
struct RefreshAction
```

## Overview

When the [refresh](EnvironmentValues/refresh.zh-Hans.md) environment value contains an instance of this structure, certain built-in views in the corresponding [Environment](Environment.zh-Hans.md) begin offering a refresh capability. They apply the instance’s handler to any refresh operation that the user initiates. By default, the environment value is `nil`, but you can use the [refreshable(action:)](View/refreshable_action.zh-Hans.md) modifier to create and store a new refresh action that uses the handler that you specify:

```swift
List(mailbox.conversations) { conversation in
    ConversationCell(conversation)
}
.refreshable {
    await mailbox.fetch()
}
```

On iOS and iPadOS, the [List](List.zh-Hans.md) in the example above offers a pull to refresh gesture because it detects the refresh action. When the user drags the list down and releases, the list calls the action’s handler. Because SwiftUI declares the handler as asynchronous, it can safely make long-running asynchronous calls, like fetching network data.

### Refreshing custom views

You can also offer refresh capability in your custom views. Read the [refresh](EnvironmentValues/refresh.zh-Hans.md) environment value to get the `RefreshAction` instance for a given [Environment](Environment.zh-Hans.md). If you find a non-`nil` value, change your view’s appearance or behavior to offer the refresh to the user, and call the instance to conduct the refresh. You can call the refresh instance directly because it defines a [callAsFunction()](RefreshAction/callAsFunction.zh-Hans.md) method that Swift calls when you call the instance:

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

Be sure to call the handler asynchronously by preceding it with `await`. Because the call is asynchronous, you can use its lifetime to indicate progress to the user. For example, you might reveal an indeterminate [ProgressView](ProgressView.zh-Hans.md) before calling the handler, and hide it when the handler completes.

If your code isn’t already in an asynchronous context, create a [doc://com.apple.documentation/documentation/Swift/Task] for the method to run in. If you do this, consider adding a way for the user to cancel the task. For more information, see [https://docs.swift.org/swift-book/LanguageGuide/Concurrency.html] in *The Swift Programming Language*.

## Calling the action

- **callAsFunction()**: Initiates a refresh action.

## Refreshing a list’s content

- **refreshable(action:)**: Marks this view as refreshable.
- **refresh**: A refresh action stored in a view’s environment.

## Conforms To

- Sendable
- SendableMetatype

