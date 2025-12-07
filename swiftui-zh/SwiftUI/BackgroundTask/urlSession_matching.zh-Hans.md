---
来源： https://developer.apple.com/documentation/SwiftUI/BackgroundTask/urlSession(匹配：)
抓取时间： 2025-12-03T06:48:17Z
---

# urlSession(matching:)

**类型方法**

响应与给定谓词匹配的后台 URL 会话的任务。

## 声明

```swift
static func urlSession(matching: @escaping (String) -> Bool) -> BackgroundTask<String, Void>
```

## 参数

- **matching**：要匹配的谓词。

## 返回值

一个后台任务，您可以使用您的应用程序或扩展处理该任务。

## 响应 URL 会话

- **urlSession**：响应后台 URL 会话的任务。
- **urlSession(_:)**：响应与给定标识符匹配的后台 URL 会话的任务。


---
source: https://developer.apple.com/documentation/SwiftUI/BackgroundTask/urlSession(matching:)
crawled: 2025-12-03T06:48:17Z
---

# urlSession(matching:)

**Type Method**

A task that responds to background URL sessions matching the given predicate.

## Declaration

```swift
static func urlSession(matching: @escaping (String) -> Bool) -> BackgroundTask<String, Void>
```

## Parameters

- **matching**: The predicate to match.

## Return Value

A background task that you can handle with your app or extension.

## Responding to URL sessions

- **urlSession**: A task that responds to background URL sessions.
- **urlSession(_:)**: A task that responds to background URL sessions matching the given identifier.

