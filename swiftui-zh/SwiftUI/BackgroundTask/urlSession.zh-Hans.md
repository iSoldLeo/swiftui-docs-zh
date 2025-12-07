---
来源： https://developer.apple.com/documentation/SwiftUI/BackgroundTask/urlSession(_:)
抓取时间： 2025-12-03T06:48:17Z
---

# urlSession(_:)

**类型 方法**

响应与给定标识符匹配的后台 URL 会话的任务。

## 声明

```swift
static func urlSession(_ identifier: String) -> BackgroundTask<Void, Void>
```

## 参数

- **identifier**：要匹配的标识符。

## 返回值

一个后台任务，您可以用自己的应用程序或扩展程序处理该任务。

## 响应 URL 会话

- **urlSession**：响应后台 URL 会话的任务。
- **urlSession(matching:)**：响应与给定谓词匹配的后台 URL 会话的任务。


---
source: https://developer.apple.com/documentation/SwiftUI/BackgroundTask/urlSession(_:)
crawled: 2025-12-03T06:48:17Z
---

# urlSession(_:)

**Type Method**

A task that responds to background URL sessions matching the given identifier.

## Declaration

```swift
static func urlSession(_ identifier: String) -> BackgroundTask<Void, Void>
```

## Parameters

- **identifier**: The identifier to match.

## Return Value

A background task that you can handle with your app or extension.

## Responding to URL sessions

- **urlSession**: A task that responds to background URL sessions.
- **urlSession(matching:)**: A task that responds to background URL sessions matching the given predicate.

