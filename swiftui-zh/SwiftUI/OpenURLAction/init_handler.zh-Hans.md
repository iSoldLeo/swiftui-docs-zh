--- 来源：https://developer.apple.com/documentation/SwiftUI/OpenURLAction/init(handler:)

抓取时间：2025-12-01T11:37:15Z

---

# init(handler:)

**Initializer**

创建一个用于打开 URL 的操作。

## 声明

```swift
@MainActor @preconcurrency init(handler: @escaping (URL) -> OpenURLAction.Result)
```

## 参数

- **handler**：要针对给定 URL 运行的闭包。该闭包接受一个 URL 作为输入，并返回一个 [Result](Result.zh-Hans.md)，指示操作的结果。

## 说明

使用此初始化器创建用于打开 URL 的自定义操作。提供一个处理程序，该处理程序接受一个 URL 并返回一个 [Result](Result.zh-Hans.md)。使用视图修饰符 [environment(_:_:)](../View/environment.zh-Hans.md) 将您的处理程序放置在环境中：

```swift
Text("Visit [Example Company](https://www.example.com) for details.")
    .environment(\.openURL, OpenURLAction { url in
        handleURL(url) // Define this method to take appropriate action.
        return .handled
    })
```

任何从环境中读取操作的视图，包括内置的 [Link](../Link.zh-Hans.md) 视图以及带有 Markdown 链接或属性字符串中链接的 [Text](../Text.zh-Hans.md) 视图，都会使用您的操作。

SwiftUI 会将您的自定义操作的处理程序返回的值转换为操作调用所需的布尔值结果。例如，使用上述操作的视图在调用该操作时会收到 `true`，因为处理程序始终返回 [handled](Result/handled.zh-Hans.md)。

## 创建操作

- **OpenURLAction.Result**：自定义打开 URL 操作的结果。


---
source: https://developer.apple.com/documentation/SwiftUI/OpenURLAction/init(handler:)
crawled: 2025-12-01T11:37:15Z
---

# init(handler:)

**Initializer**

Creates an action that opens a URL.

## Declaration

```swift
@MainActor @preconcurrency init(handler: @escaping (URL) -> OpenURLAction.Result)
```

## Parameters

- **handler**: The closure to run for the given URL. The closure takes a URL as input, and returns a [Result](Result.zh-Hans.md) that indicates the outcome of the action.

## Discussion

Use this initializer to create a custom action for opening URLs. Provide a handler that takes a URL and returns an [Result](Result.zh-Hans.md). Place your handler in the environment using the [environment(_:_:)](../View/environment.zh-Hans.md) view modifier:

```swift
Text("Visit [Example Company](https://www.example.com) for details.")
    .environment(\.openURL, OpenURLAction { url in
        handleURL(url) // Define this method to take appropriate action.
        return .handled
    })
```

Any views that read the action from the environment, including the built-in [Link](../Link.zh-Hans.md) view and [Text](../Text.zh-Hans.md) views with markdown links, or links in attributed strings, use your action.

SwiftUI translates the value that your custom action’s handler returns into an appropriate Boolean result for the action call. For example, a view that uses the action declared above receives `true` when calling the action, because the handler always returns [handled](Result/handled.zh-Hans.md).

## Creating the action

- **OpenURLAction.Result**: The result of a custom open URL action.

