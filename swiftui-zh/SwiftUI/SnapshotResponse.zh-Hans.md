--- 来源：https://developer.apple.com/documentation/SwiftUI/SnapshotResponse
抓取时间：2025-12-02T17:43:31Z

---

# SnapshotResponse

**Structure**

您的应用程序对快照后台任务的响应。

## 声明

```swift
struct SnapshotResponse
```

## 创建响应

- **init(restoredDefaultState:estimatedSnapshotExpiration:identifier:)**：创建快照响应。

## 处理后台任务

- **backgroundTask(_:action:)**：当系统提供后台任务时，运行指定的操作。

- **BackgroundTask**：您的应用程序或扩展程序可以处理的后台任务类型。

- **SnapshotData**：快照后台任务的关联数据。

## 符合以下规范

- Sendable

- SendableMetatype


---
source: https://developer.apple.com/documentation/SwiftUI/SnapshotResponse
crawled: 2025-12-02T17:43:31Z
---

# SnapshotResponse

**Structure**

Your application’s response to a snapshot background task.

## Declaration

```swift
struct SnapshotResponse
```

## Creating a response

- **init(restoredDefaultState:estimatedSnapshotExpiration:identifier:)**: Creates a snapshot response.

## Handling background tasks

- **backgroundTask(_:action:)**: Runs the specified action when the system provides a background task.
- **BackgroundTask**: The kinds of background tasks that your app or extension can handle.
- **SnapshotData**: The associated data of a snapshot background task.

## Conforms To

- Sendable
- SendableMetatype

