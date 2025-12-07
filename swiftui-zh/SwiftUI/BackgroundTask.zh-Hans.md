--- 来源：https://developer.apple.com/documentation/SwiftUI/BackgroundTask

抓取时间：2025-12-02T17:43:29Z

---

# BackgroundTask

**Structure**

您的应用或扩展程序可以处理的后台任务类型。

## 声明

```swift
struct BackgroundTask<Request, Response>
```

## 概述

将此类型的值与 [backgroundTask(_:action:)](scene/backgroundTask___action.zh-Hans.md) 场景修饰符一起使用，可以为系统发送给您的应用或扩展程序的后台任务创建处理程序。例如，您可以使用 [urlSession](BackgroundTask/urlSession.zh-Hans.md) 定义一个异步闭包，系统在启动您的应用或扩展程序时会调用该闭包来处理来自后台 [doc://com.apple.documentation/documentation/Foundation/URLSession] 的响应。

## 刷新应用

- **appRefresh**：在后台更新应用状态的任务。

- **appRefresh(_:)**：在后台更新应用状态（针对匹配的标识符）的任务。

## 准备快照

- **snapshot**：用于更新应用用户界面以准备快照的后台任务。

## 接收连接更新

- **bluetoothAlert**：用于接收来自已配对蓝牙配件的关键警报的后台任务。

- **watchConnectivity**：用于接收来自 Watch Connectivity 框架的后台更新的后台任务。

## 响应 URL 会话

- **urlSession**：响应后台 URL 会话的任务。

- **urlSession(_:)**：响应与给定标识符匹配的后台 URL 会话的任务。

- **urlSession(matching:)**：响应与给定谓词匹配的后台 URL 会话的任务。

## 更新 Intent 和快捷指令

- **intentDidRun**：用于在 SiriKit Intent 运行后更新应用的后台任务。

- **relevantShortcut**：用于定期提供相关 Siri 快捷指令的后台任务。

## 处理后台任务

- **backgroundTask(_:action:)**：当系统提供后台任务时，运行指定的操作。

- **SnapshotData**：快照后台任务的关联数据。

- **SnapshotResponse**：应用对快照后台任务的响应。

## 符合以下规范

- Sendable

- SendableMetatype


---
source: https://developer.apple.com/documentation/SwiftUI/BackgroundTask
crawled: 2025-12-02T17:43:29Z
---

# BackgroundTask

**Structure**

The kinds of background tasks that your app or extension can handle.

## Declaration

```swift
struct BackgroundTask<Request, Response>
```

## Overview

Use a value of this type with the [backgroundTask(_:action:)](scene/backgroundTask___action.zh-Hans.md) scene modifier to create a handler for background tasks that the system sends to your app or extension. For example, you can use [urlSession](BackgroundTask/urlSession.zh-Hans.md) to define an asynchronous closure that the system calls when it launches your app or extension to handle a response from a background [doc://com.apple.documentation/documentation/Foundation/URLSession].

## Refreshing the app

- **appRefresh**: A task that updates your app’s state in the background.
- **appRefresh(_:)**: A task that updates your app’s state in the background for a matching identifier.

## Preparing for a snapshot

- **snapshot**: A background task used to update your app’s user interface in preparation for a snapshot.

## Receiving connectivity updates

- **bluetoothAlert**: A background task used to receive critical alerts from paired bluetooth accessories.
- **watchConnectivity**: A background task used to receive background updates from the Watch Connectivity framework.

## Responding to URL sessions

- **urlSession**: A task that responds to background URL sessions.
- **urlSession(_:)**: A task that responds to background URL sessions matching the given identifier.
- **urlSession(matching:)**: A task that responds to background URL sessions matching the given predicate.

## Updating intents and shortcuts

- **intentDidRun**: A background task used to update your app after a SiriKit intent runs.
- **relevantShortcut**: A background task used to periodically donate relevant Siri shortcuts.

## Handling background tasks

- **backgroundTask(_:action:)**: Runs the specified action when the system provides a background task.
- **SnapshotData**: The associated data of a snapshot background task.
- **SnapshotResponse**: Your application’s response to a snapshot background task.

## Conforms To

- Sendable
- SendableMetatype

