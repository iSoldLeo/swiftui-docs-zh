---
来源： https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/openURL
抓取时间： 2025-12-02T17:43:23Z
---

# openURL

**实例属性**

打开 URL 的操作。

## 声明

```swift
@MainActor @preconcurrency var openURL: OpenURLAction { get set }
```

## 讨论

读取该环境值可获得给定[OpenURLAction](../OpenURLAction.zh-Hans.md) 的[Environment](../Environment.zh-Hans.md) 实例。调用该实例打开 URL。您直接调用实例是因为它定义了一个 [callAsFunction(_:)](../OpenURLAction/callAsFunction.zh-Hans.md) 方法，当您调用实例时，Swift 会调用该方法。

例如，您可以在用户点击按钮时打开一个网站：

```swift
struct OpenURLExample: View {
    @Environment(\.openURL) private var openURL

    var body: some View {
        Button {
            if let url = URL(string: "https://www.example.com") {
                openURL(url)
            }
        } label: {
            Label("Get Help", systemImage: "person.fill.questionmark")
        }
    }
}
```

如果想知道操作是否成功，可以添加一个取布尔值的完成处理程序。在这种情况下，Swift 会隐式调用[callAsFunction(_:completion:)](../OpenURLAction/callAsFunction___completion.zh-Hans.md) 方法。该方法会在确定是否可以打开 URL 后调用您的完成处理程序，但可能会在完成打开 URL 之前调用。您可以在上面的示例中添加一个处理程序，以便将结果打印到控制台：

```swift
openURL(url) { accepted in
    print(accepted ? "Success" : "Failure")
}
```

系统提供了一个默认的打开 URL 操作，其行为取决于 URL 的内容。例如，如果可能，默认操作会在相关应用程序中打开通用链接；如果不可能，则会在用户的默认网络浏览器中打开通用链接。

您还可以使用[environment(_:_:)](../View/environment.zh-Hans.md) 视图修饰符设置自定义操作。任何从环境中读取动作的视图，包括内置的 [Link](../Link.zh-Hans.md) 视图和带有标记符链接或归属字符串中链接的 [Text](../Text.zh-Hans.md) 视图，都会使用你的动作。通过调用[init(handler:)](../OpenURLAction/init_handler.zh-Hans.md) 初始化器和接收 URL 并返回[Result](../OpenURLAction/Result.zh-Hans.md) 的处理程序来初始化操作：

```swift
Text("Visit [Example Company](https://www.example.com) for details.")
    .environment(\.openURL, OpenURLAction { url in
        handleURL(url) // Define this method to take appropriate action.
        return .handled
    })
```

SwiftUI 会将自定义操作处理程序返回的值转换为操作调用的适当布尔结果。例如，使用上面声明的操作的视图在调用该操作时会收到 `true`，因为处理程序总是返回 [handled](../OpenURLAction/Result/handled.zh-Hans.md)。

## 发送和接收 URL

- **OpenURLAction**：打开 URL 的操作。
- **onOpenURL(perform:)**：注册一个处理程序，以调用该处理程序来响应应用程序收到的 URL。


---
source: https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/openURL
crawled: 2025-12-02T17:43:23Z
---

# openURL

**Instance Property**

An action that opens a URL.

## Declaration

```swift
@MainActor @preconcurrency var openURL: OpenURLAction { get set }
```

## Discussion

Read this environment value to get an [OpenURLAction](../OpenURLAction.zh-Hans.md) instance for a given [Environment](../Environment.zh-Hans.md). Call the instance to open a URL. You call the instance directly because it defines a [callAsFunction(_:)](../OpenURLAction/callAsFunction.zh-Hans.md) method that Swift calls when you call the instance.

For example, you can open a web site when the user taps a button:

```swift
struct OpenURLExample: View {
    @Environment(\.openURL) private var openURL

    var body: some View {
        Button {
            if let url = URL(string: "https://www.example.com") {
                openURL(url)
            }
        } label: {
            Label("Get Help", systemImage: "person.fill.questionmark")
        }
    }
}
```

If you want to know whether the action succeeds, add a completion handler that takes a Boolean value. In this case, Swift implicitly calls the [callAsFunction(_:completion:)](../OpenURLAction/callAsFunction___completion.zh-Hans.md) method instead. That method calls your completion handler after it determines whether it can open the URL, but possibly before it finishes opening the URL. You can add a handler to the example above so that it prints the outcome to the console:

```swift
openURL(url) { accepted in
    print(accepted ? "Success" : "Failure")
}
```

The system provides a default open URL action with behavior that depends on the contents of the URL. For example, the default action opens a Universal Link in the associated app if possible, or in the user’s default web browser if not.

You can also set a custom action using the [environment(_:_:)](../View/environment.zh-Hans.md) view modifier. Any views that read the action from the environment, including the built-in [Link](../Link.zh-Hans.md) view and [Text](../Text.zh-Hans.md) views with markdown links, or links in attributed strings, use your action. Initialize an action by calling the [init(handler:)](../OpenURLAction/init_handler.zh-Hans.md) initializer with a handler that takes a URL and returns an [Result](../OpenURLAction/Result.zh-Hans.md):

```swift
Text("Visit [Example Company](https://www.example.com) for details.")
    .environment(\.openURL, OpenURLAction { url in
        handleURL(url) // Define this method to take appropriate action.
        return .handled
    })
```

SwiftUI translates the value that your custom action’s handler returns into an appropriate Boolean result for the action call. For example, a view that uses the action declared above receives `true` when calling the action, because the handler always returns [handled](../OpenURLAction/Result/handled.zh-Hans.md).

## Sending and receiving URLs

- **OpenURLAction**: An action that opens a URL.
- **onOpenURL(perform:)**: Registers a handler to invoke in response to a URL that your app receives.

