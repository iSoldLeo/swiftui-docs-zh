--- 来源：https://developer.apple.com/documentation/SwiftUI/SnapshotData/SnapshotReason
抓取时间：2025-12-03T06:48:21Z

---

# SnapshotData.SnapshotReason

**Enumeration**

后台快照任务的原因。

## 声明

```swift
enum SnapshotReason
```

## 获取快照原因

- **SnapshotData.SnapshotReason.appBackgrounded**：应用从前台切换到后台。

- **SnapshotData.SnapshotReason.appScheduled**：应用已安排此快照。

- **SnapshotData.SnapshotReason.complicationUpdate**：应用已更新复杂功能时间线。

- **SnapshotData.SnapshotReason.prelaunch**：系统需要 Dock 栏的快照，但应用尚未启动。

- **SnapshotData.SnapshotReason.returnToDefaultState**：用户上次与应用交互已超过一小时；应用的快照应恢复到默认状态。

## 获取数据

- **identifier**：与此快照请求关联的标识符。

- **reason**：后台快照任务的原因。

## 符合以下规范

- Copyable

- Equatable

- Hashable

- Sendable

- SendableMetatype


---
source: https://developer.apple.com/documentation/SwiftUI/SnapshotData/SnapshotReason
crawled: 2025-12-03T06:48:21Z
---

# SnapshotData.SnapshotReason

**Enumeration**

The reason for a background snapshot task.

## Declaration

```swift
enum SnapshotReason
```

## Getting the snapshot reasons

- **SnapshotData.SnapshotReason.appBackgrounded**: The app transitioned from the foreground to the background.
- **SnapshotData.SnapshotReason.appScheduled**: The app scheduled this snapshot.
- **SnapshotData.SnapshotReason.complicationUpdate**: The app updated the complication timeline.
- **SnapshotData.SnapshotReason.prelaunch**: The system needs a snapshot for the dock, but the app has not been launched yet.
- **SnapshotData.SnapshotReason.returnToDefaultState**: It has been more than an hour since the user’s last interaction with the app; the app’s snapshot should return to its default state.

## Getting the data

- **identifier**: The identifier associated with this snapshot request.
- **reason**: The reason for a background snapshot task.

## Conforms To

- Copyable
- Equatable
- Hashable
- Sendable
- SendableMetatype

