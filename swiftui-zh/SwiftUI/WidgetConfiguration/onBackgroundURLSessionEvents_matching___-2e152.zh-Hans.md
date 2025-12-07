---
来源：https://developer.apple.com/documentation/SwiftUI/WidgetConfiguration/onBackgroundURLSessionEvents(匹配:_:)-2e152
抓取时间：2025-11-30T23:27:25Z


# onBackgroundURLSessionEvents(matching:_:)

**实例方法**

当与闭包标识的 URL 会话相关的事件等待处理时，添加一个要执行的操作。

## 声明

```swift
@MainActor @preconcurrency func onBackgroundURLSessionEvents(matching matchingBlock: ((String) -> Bool)? = nil, _ urlSessionEvent: @escaping (String, @escaping () -> Void) -> Void) -> some WidgetConfiguration

```

## 参数

- **urlSessionEvent**：一个包含名为 `identifier` 的字符串参数和名为 `completion` 的闭包。

## 返回值

当具有指定标识符的`URLSession` 发生事件时，触发`urlSessionEvent` 的 widget。

### 讨论

当 widget 发起后台网络请求时，系统会将与请求相关的事件直接发送到 widget 扩展，而不是发送到包含它的应用程序。要处理这些事件，请执行以下操作：

1.使用 `identifier` 参数确定是否存在相应的 `URLSession` 对象。如果系统尚未终止 widget 扩展，则应保持对用于原始后台网络请求的同一`URLSession` 对象的引用。如果系统终止了您的 widget 扩展，请使用该标识符创建一个新的`URLSession` 对象，以便它能接收事件。您可以考虑将`URLSession` 对象懒散地初始化并缓存在一个中心位置，这样无论扩展是处于活动状态、暂停状态还是终止状态，您的代码都能正常工作。
2.存储对`completion` 闭包的引用，以便在系统发送所有事件后调用它。
3.在系统调用`URLSession` 委托的[doc://com.apple.documentation/documentation/Foundation/URLSessionDelegate/urlSessionDidFinishEvents(forBackgroundURLSession:)] 方法后，调用`completion` 闭包。


---
source: https://developer.apple.com/documentation/SwiftUI/WidgetConfiguration/onBackgroundURLSessionEvents(matching:_:)-2e152
crawled: 2025-11-30T23:27:25Z
---

# onBackgroundURLSessionEvents(matching:_:)

**Instance Method**

Adds an action to perform when events related to a URL session identified by a closure are waiting to be processed.

## Declaration

```swift
@MainActor @preconcurrency func onBackgroundURLSessionEvents(matching matchingBlock: ((String) -> Bool)? = nil, _ urlSessionEvent: @escaping (String, @escaping () -> Void) -> Void) -> some WidgetConfiguration

```

## Parameters

- **urlSessionEvent**: A closure that takes a string parameter called `identifier` and a closure called `completion`.

## Return Value

A widget that triggers `urlSessionEvent` when events are generated for a `URLSession` with the specified identifier.

## Discussion

When a widget initiates a background network request, the system delivers events related to the request directly to the widget extension instead of the containing app. To process the events, do the following:

1. Use the `identifier` parameter to determine if a corresponding `URLSession` object exists. If the system hasn’t terminated your widget extension, maintain a reference to the same `URLSession` object you used for the original background network request. If the system terminated your widget extension, use the identifier to create a new `URLSession` object so it can receive the events. You might consider lazily initializing, and caching, the `URLSession` objects in a central location so that your code works regardless of whether your extension remains active, is suspended, or is terminated.
2. Store a reference to the `completion` closure to invoke it after the system delivers all events.
3. After the system calls the `URLSession` delegate’s [doc://com.apple.documentation/documentation/Foundation/URLSessionDelegate/urlSessionDidFinishEvents(forBackgroundURLSession:)] method, invoke the `completion` closure.

