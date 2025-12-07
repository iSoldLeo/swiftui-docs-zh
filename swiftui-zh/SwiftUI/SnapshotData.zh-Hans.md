--- 来源：https://developer.apple.com/documentation/SwiftUI/SnapshotData
抓取时间：2025-12-02T17:43:30Z

---

# SnapshotData

**Structure**

快照后台任务的关联数据。

## 声明

```swift
struct SnapshotData
```

## 获取数据

- **identifier**：与此快照请求关联的标识符。

- **reason**：后台快照任务的原因。

- **SnapshotData.SnapshotReason**：后台快照任务的原因。

## 处理后台任务

- **backgroundTask(_:action:)**：当系统提供后台任务时，运行指定的操作。

- **BackgroundTask**：您的应用或扩展程序可以处理的后台任务类型。

- **SnapshotResponse**：您的应用对快照后台任务的响应。

## 符合以下协议：

- Sendable

- SendableMetatype


---
source: https://developer.apple.com/documentation/SwiftUI/SnapshotData
crawled: 2025-12-02T17:43:30Z
---

# SnapshotData

**Structure**

The associated data of a snapshot background task.

## Declaration

```swift
struct SnapshotData
```

## Getting the data

- **identifier**: The identifier associated with this snapshot request.
- **reason**: The reason for a background snapshot task.
- **SnapshotData.SnapshotReason**: The reason for a background snapshot task.

## Handling background tasks

- **backgroundTask(_:action:)**: Runs the specified action when the system provides a background task.
- **BackgroundTask**: The kinds of background tasks that your app or extension can handle.
- **SnapshotResponse**: Your application’s response to a snapshot background task.

## Conforms To

- Sendable
- SendableMetatype

