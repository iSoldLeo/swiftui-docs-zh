---
源：https://developer.apple.com/documentation/SwiftUI/SnapshotResponse/init(restoredDefaultState:estimateSnapshotExpiration:identifier:)
抓取时间：2025-12-01T11:37:36Z


# init(restoredDefaultState:estimatedSnapshotExpiration:identifier:)

**Initializer**

创建快照响应。

## 声明

```swift
init(restoredDefaultState: Bool = false, estimatedSnapshotExpiration: Date? = nil, identifier: String? = nil)
```

## 参数

- **restoredDefaultState**：`true`： 如果应用程序已返回默认启动场景，则传递 `true`。
- **estimatedSnapshotExpiration**：下一次刷新后台快照任务的首选日期和时间。如果不想安排下一次刷新，请使用 [doc://com.apple.documentation/documentation/Foundation/Date/distantFuture]。
- **identifier**：与下一个后台快照刷新任务相关联的自定义字符串。此值将分配给下一个快照任务的 `TaskData` userInfo 属性。如果不想将任何标识符与下一个任务相关联，则传递`nil`。


---
source: https://developer.apple.com/documentation/SwiftUI/SnapshotResponse/init(restoredDefaultState:estimatedSnapshotExpiration:identifier:)
crawled: 2025-12-01T11:37:36Z
---

# init(restoredDefaultState:estimatedSnapshotExpiration:identifier:)

**Initializer**

Creates a snapshot response.

## Declaration

```swift
init(restoredDefaultState: Bool = false, estimatedSnapshotExpiration: Date? = nil, identifier: String? = nil)
```

## Parameters

- **restoredDefaultState**: Pass `true` if your app has navigated back to its default launch scene.
- **estimatedSnapshotExpiration**: The preferred date and time for the next background snapshot refresh task. Use [doc://com.apple.documentation/documentation/Foundation/Date/distantFuture] if you don’t want to schedule the next refresh.
- **identifier**: A custom string to associate with the next background snapshot refresh task. This value is assigned to the next snapshot task’s `TaskData` userInfo property. Pass `nil` if you don’t want to associate any identifier with the next task.

