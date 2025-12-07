--- 来源：https://developer.apple.com/documentation/SwiftUI/View/onOpenURL(perform:)

抓取时间：2025-11-30T21:28:26Z

---

# onOpenURL(perform:)

**实例方法**

注册一个处理程序，用于响应应用接收到的 URL。

## 声明

```swift
nonisolated func onOpenURL(perform action: @escaping (URL) -> ()) -> some View

```

## 参数

- **action**：当应用接收到通用链接或自定义链接时，SwiftUI 会调用此闭包。[doc://com.apple.documentation/documentation/Foundation/URL] 会将 URL 作为输入参数。

## 返回值

一个用于处理传入 URL 的视图。

## 说明

使用此视图修饰符可以在应用的特定场景中接收 URL。 SwiftUI 将传入的 URL 路由到的场景取决于您的应用结构、当前激活的场景以及其他配置。更多信息，请参阅 [handlesExternalEvents(matching:)](../scene/handlesExternalEvents_matching.zh-Hans.md)。

传统的 UI 框架使用 [doc://com.apple.documentation/documentation/Foundation/NSUserActivity] 将通用链接传递给您的应用。但是，SwiftUI 直接将通用链接作为 URL 传递给您的应用，您可以使用此修饰符接收该 URL。要接收其他用户活动（例如，当您的应用参与 Handoff 时），请改用 [onContinueUserActivity(_:perform:)](onContinueUserActivity___perform.zh-Hans.md) 修饰符。

有关链接到您的应用的更多信息，请参阅 [doc://com.apple.documentation/documentation/Xcode/allowing-apps-and-websites-to-link-to-your-content]。

## 发送和接收 URL

- **openURL**：打开 URL 的操作。

- **OpenURLAction**：打开 URL 的操作。


---
source: https://developer.apple.com/documentation/SwiftUI/View/onOpenURL(perform:)
crawled: 2025-11-30T21:28:26Z
---

# onOpenURL(perform:)

**Instance Method**

Registers a handler to invoke in response to a URL that your app receives.

## Declaration

```swift
nonisolated func onOpenURL(perform action: @escaping (URL) -> ()) -> some View

```

## Parameters

- **action**: A closure that SwiftUI calls when your app receives a Universal Link or a custom [doc://com.apple.documentation/documentation/Foundation/URL]. The closure takes the URL as an input parameter.

## Return Value

A view that handles incoming URLs.

## Discussion

Use this view modifier to receive URLs in a particular scene within your app. The scene that SwiftUI routes the incoming URL to depends on the structure of your app, what scenes are active, and other configuration. For more information, see [handlesExternalEvents(matching:)](../scene/handlesExternalEvents_matching.zh-Hans.md).

UI frameworks traditionally pass Universal Links to your app using an [doc://com.apple.documentation/documentation/Foundation/NSUserActivity]. However, SwiftUI passes a Universal Link to your app directly as a URL, which you receive using this modifier. To receive other user activities, like when your app participates in Handoff, use the [onContinueUserActivity(_:perform:)](onContinueUserActivity___perform.zh-Hans.md) modifier instead.

For more information about linking into your app, see [doc://com.apple.documentation/documentation/Xcode/allowing-apps-and-websites-to-link-to-your-content].

## Sending and receiving URLs

- **openURL**: An action that opens a URL.
- **OpenURLAction**: An action that opens a URL.

