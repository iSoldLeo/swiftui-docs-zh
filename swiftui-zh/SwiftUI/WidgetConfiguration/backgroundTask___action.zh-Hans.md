---
来源：https://developer.apple.com/documentation/SwiftUI/WidgetConfiguration/backgroundTask(_:action:)
抓取时间： 2025-12-02T19:43:02Z
---

# backgroundTask(_:action:)

**实例方法**

当系统提供后台任务时，运行给定的操作。

## 声明

```swift
nonisolated func backgroundTask<D, R>(_ task: BackgroundTask<D, R>, action: @escaping (D) async -> R) -> some WidgetConfiguration where D : Sendable, R : Sendable

```

## 参数

- **task**：操作响应的任务类型。
- **action**：当系统提供与所提供任务相匹配的任务时调用的闭包。

### 讨论

当系统为一个或多个后台任务唤醒您的应用程序或扩展时，它会调用与匹配任务相关的任何操作。当您的异步操作返回时，系统会将您的应用程序重新置于暂停状态。在 Widget 扩展中，该修改器可用于使用 [urlSession](../BackgroundTask/urlSession.zh-Hans.md) 处理 URL 会话后台任务。

## 管理后台任务

- **onBackgroundURLSessionEvents(matching:_:)**：当与闭包标识的 URL 会话相关的事件等待处理时，添加一个要执行的操作。


---
source: https://developer.apple.com/documentation/SwiftUI/WidgetConfiguration/backgroundTask(_:action:)
crawled: 2025-12-02T19:43:02Z
---

# backgroundTask(_:action:)

**Instance Method**

Runs the given action when the system provides a background task.

## Declaration

```swift
nonisolated func backgroundTask<D, R>(_ task: BackgroundTask<D, R>, action: @escaping (D) async -> R) -> some WidgetConfiguration where D : Sendable, R : Sendable

```

## Parameters

- **task**: The type of task the action responds to.
- **action**: The closure that is called when the system provides a task matching the provided task.

## Discussion

When the system wakes your app or extension for one or more background tasks, it will call any actions associated with matching tasks. When your async actions return, the system will put your app back into a suspended state. In Widget Extensions, this modifier can be used to handle URL Session background tasks with [urlSession](../BackgroundTask/urlSession.zh-Hans.md).

## Managing background tasks

- **onBackgroundURLSessionEvents(matching:_:)**: Adds an action to perform when events related to a URL session identified by a closure are waiting to be processed.

