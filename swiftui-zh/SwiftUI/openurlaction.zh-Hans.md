--- 来源：https://developer.apple.com/documentation/swiftui/openurlaction
抓取时间：2025-12-04T13:39:38Z
---

# OpenURLAction

**Structure**

一个用于打开 URL 的操作。

## 声明

```swift
@MainActor @preconcurrency struct OpenURLAction
```

## 概述

读取 [openURL](EnvironmentValues/openURL.zh-Hans.md) 环境变量值，获取给定 [Environment](Environment.zh-Hans.md) 对应的结构体实例。调用该实例即可打开 URL。之所以直接调用实例，是因为它定义了一个 [callAsFunction(_:)](OpenURLAction/callAsFunction.zh-Hans.md) 方法，Swift 会在调用该实例时调用该方法。

例如，您可以让用户点击按钮时打开一个网站：

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

如果您想知道操作是否成功，请添加一个接受布尔值的完成处理程序。在这种情况下，Swift 会隐式调用 [callAsFunction(_:completion:)](OpenURLAction/callAsFunction___completion.zh-Hans.md) 方法。该方法会在确定是否可以打开 URL 之后（但可能在 URL 打开完成之前）调用您的完成处理程序。您可以为上面的示例添加一个处理程序，以便将结果打印到控制台：

```swift
openURL(url) { accepted in
    print(accepted ? "Success" : "Failure")
}
```

系统提供了一个默认的打开 URL 操作，其行为取决于 URL 的内容。例如，默认操作会在可能的情况下在关联的应用程序中打开通用链接，否则会在用户的默认浏览器中打开。

您还可以使用 [environment(_:_:)](View/environment.zh-Hans.md) 视图修饰符设置自定义操作。任何从环境中读取操作的视图，包括内置的 [Link](Link.zh-Hans.md) 视图和带有 Markdown 链接或属性字符串中链接的 [Text](Text.zh-Hans.md) 视图，都会使用您的操作。要初始化操作，请调用 [init(handler:)](OpenURLAction/init_handler.zh-Hans.md) 初始化器，并传入一个接受 URL 并返回 [Result](OpenURLAction/Result.zh-Hans.md) 的处理程序：

```swift
Text("Visit [Example Company](https://www.example.com) for details.")
    .environment(\.openURL, OpenURLAction { url in
        handleURL(url) // Define this method to take appropriate action.
        return .handled
    })
```

SwiftUI 会将自定义操作的处理程序返回的值转换为操作调用所需的布尔值。例如，使用上述操作的视图在调用该操作时会收到 `true`，因为处理程序始终返回 [handled](OpenURLAction/Result/handled.zh-Hans.md)。

## 创建操作

- **init(handler:)**：创建一个打开 URL 的操作。

- **OpenURLAction.Result**：自定义打开 URL 操作的结果。

## 调用操作

- **callAsFunction(_:)**：按照系统约定打开 URL。

- **callAsFunction(_:completion:)**：按照系统约定异步打开 URL。

## 实例方法

- **callAsFunction(_:prefersInApp:)**

## 发送和接收 URL

- **openURL**：打开 URL 的操作。

- **onOpenURL(perform:)**：注册一个处理程序，以便在应用接收到 URL 时调用。

## 符合以下协议：

- Sendable

- SendableMetatype


---
source: https://developer.apple.com/documentation/swiftui/openurlaction
crawled: 2025-12-04T13:39:38Z
---

# OpenURLAction

**Structure**

An action that opens a URL.

## Declaration

```swift
@MainActor @preconcurrency struct OpenURLAction
```

## Overview

Read the [openURL](EnvironmentValues/openURL.zh-Hans.md) environment value to get an instance of this structure for a given [Environment](Environment.zh-Hans.md). Call the instance to open a URL. You call the instance directly because it defines a [callAsFunction(_:)](OpenURLAction/callAsFunction.zh-Hans.md) method that Swift calls when you call the instance.

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

If you want to know whether the action succeeds, add a completion handler that takes a Boolean value. In this case, Swift implicitly calls the [callAsFunction(_:completion:)](OpenURLAction/callAsFunction___completion.zh-Hans.md) method instead. That method calls your completion handler after it determines whether it can open the URL, but possibly before it finishes opening the URL. You can add a handler to the example above so that it prints the outcome to the console:

```swift
openURL(url) { accepted in
    print(accepted ? "Success" : "Failure")
}
```

The system provides a default open URL action with behavior that depends on the contents of the URL. For example, the default action opens a Universal Link in the associated app if possible, or in the user’s default web browser if not.

You can also set a custom action using the [environment(_:_:)](View/environment.zh-Hans.md) view modifier. Any views that read the action from the environment, including the built-in [Link](Link.zh-Hans.md) view and [Text](Text.zh-Hans.md) views with markdown links, or links in attributed strings, use your action. Initialize an action by calling the [init(handler:)](OpenURLAction/init_handler.zh-Hans.md) initializer with a handler that takes a URL and returns an [Result](OpenURLAction/Result.zh-Hans.md):

```swift
Text("Visit [Example Company](https://www.example.com) for details.")
    .environment(\.openURL, OpenURLAction { url in
        handleURL(url) // Define this method to take appropriate action.
        return .handled
    })
```

SwiftUI translates the value that your custom action’s handler returns into an appropriate Boolean result for the action call. For example, a view that uses the action declared above receives `true` when calling the action, because the handler always returns [handled](OpenURLAction/Result/handled.zh-Hans.md).

## Creating the action

- **init(handler:)**: Creates an action that opens a URL.
- **OpenURLAction.Result**: The result of a custom open URL action.

## Calling the action

- **callAsFunction(_:)**: Opens a URL, following system conventions.
- **callAsFunction(_:completion:)**: Asynchronously opens a URL, following system conventions.

## Instance Methods

- **callAsFunction(_:prefersInApp:)**

## Sending and receiving URLs

- **openURL**: An action that opens a URL.
- **onOpenURL(perform:)**: Registers a handler to invoke in response to a URL that your app receives.

## Conforms To

- Sendable
- SendableMetatype

