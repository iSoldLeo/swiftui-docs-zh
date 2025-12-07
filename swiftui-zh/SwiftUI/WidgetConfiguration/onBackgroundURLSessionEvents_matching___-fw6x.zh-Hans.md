---
来源：https://developer.apple.com/documentation/SwiftUI/WidgetConfiguration/onBackgroundURLSessionEvents(匹配:_:)-fw6x
抓取时间： 2025-12-02T19:43:04Z
---

# onBackgroundURLSessionEvents(matching:_:)

**实例方法**

当与具有匹配标识符的 URL 会话相关的事件等待处理时，添加一个要执行的操作。

## 声明

```swift
@MainActor @preconcurrency func onBackgroundURLSessionEvents(matching matchingString: String, _ urlSessionEvent: @escaping (String, @escaping () -> Void) -> Void) -> some WidgetConfiguration

```

## 参数

- **matchingString**：要监控事件的 URL 会话的标识符。
- **urlSessionEvent**：闭包，以字符串标识符和名为`completion` 的闭包为参数。

## 返回值

当具有指定标识符的`URLSession` 发生事件时，触发`urlSessionEvent` 的 widget。

### 讨论

当 widget 发起后台网络请求时，系统会将与请求相关的事件直接发送到 widget 扩展，而不是发送到包含它的应用程序。要处理这些事件，请执行以下操作：

1.使用 `matching` 参数确定是否存在相应的 `URLSession` 对象。如果系统尚未终止 widget 扩展，则应保持对用于原始后台网络请求的同一`URLSession` 对象的引用。如果系统终止了您的 widget 扩展，请使用该标识符创建一个新的`URLSession` 对象，以便它能接收事件。您可以考虑将`URLSession` 对象懒散地初始化并缓存在一个中心位置，这样无论扩展是处于活动状态、暂停状态还是终止状态，您的代码都能正常工作。
2.存储对`completion` 闭包`urlSessionEvent` 的引用，以便在系统发送所有事件后调用它。
3.在系统调用`URLSession` 委托的[doc://com.apple.documentation/documentation/Foundation/URLSessionDelegate/urlSessionDidFinishEvents(forBackgroundURLSession:)] 方法后，调用`completion` 闭包。


---
source: https://developer.apple.com/documentation/SwiftUI/WidgetConfiguration/onBackgroundURLSessionEvents(matching:_:)-fw6x
crawled: 2025-12-02T19:43:04Z
---

# onBackgroundURLSessionEvents(matching:_:)

**Instance Method**

Adds an action to perform when events related to a URL session with a matching identifier are waiting to be processed.

## Declaration

```swift
@MainActor @preconcurrency func onBackgroundURLSessionEvents(matching matchingString: String, _ urlSessionEvent: @escaping (String, @escaping () -> Void) -> Void) -> some WidgetConfiguration

```

## Parameters

- **matchingString**: The identifier of a URL session to monitor for events.
- **urlSessionEvent**: A closure that takes a string identifier and a closure called `completion` as parameters.

## Return Value

A widget that triggers `urlSessionEvent` when events are generated for a `URLSession` with the specified identifier.

## Discussion

When a widget initiates a background network request, the system delivers events related to the request directly to the widget extension instead of the containing app. To process the events, do the following:

1. Use the `matching` parameter to determine if a corresponding `URLSession` object exists. If the system hasn’t terminated your widget extension, maintain a reference to the same `URLSession` object you used for the original background network request. If the system terminated your widget extension, use the identifier to create a new `URLSession` object so it can receive the events. You might consider lazily initializing, and caching, the `URLSession` objects in a central location so that your code works regardless of whether your extension remains active, is suspended, or is terminated.
2. Store a reference to the `completion` closure of `urlSessionEvent` to invoke it after the system delivers all events.
3. After the system calls the `URLSession` delegate’s [doc://com.apple.documentation/documentation/Foundation/URLSessionDelegate/urlSessionDidFinishEvents(forBackgroundURLSession:)] method, invoke the `completion` closure.

