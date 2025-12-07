--- 来源：https://developer.apple.com/documentation/SwiftUI/SnapshotData/SnapshotReason/appBackgrounded

抓取时间：2025-12-04T13:39:39Z

---

# SnapshotData.SnapshotReason.appBackgrounded

**Case**

应用从前台切换到后台。

## 声明

```swift
case appBackgrounded
```

## 获取快照原因

- **SnapshotData.SnapshotReason.appScheduled**：应用已安排此快照。

- **SnapshotData.SnapshotReason.complicationUpdate**：应用已更新复杂功能时间线。

- **SnapshotData.SnapshotReason.prelaunch**：系统需要 Dock 栏快照，但应用尚未启动。

- **SnapshotData.SnapshotReason.returnToDefaultState**：用户上次与应用交互已超过一小时；应用的快照应恢复到默认状态。


---
source: https://developer.apple.com/documentation/SwiftUI/SnapshotData/SnapshotReason/appBackgrounded
crawled: 2025-12-04T13:39:39Z
---

# SnapshotData.SnapshotReason.appBackgrounded

**Case**

The app transitioned from the foreground to the background.

## Declaration

```swift
case appBackgrounded
```

## Getting the snapshot reasons

- **SnapshotData.SnapshotReason.appScheduled**: The app scheduled this snapshot.
- **SnapshotData.SnapshotReason.complicationUpdate**: The app updated the complication timeline.
- **SnapshotData.SnapshotReason.prelaunch**: The system needs a snapshot for the dock, but the app has not been launched yet.
- **SnapshotData.SnapshotReason.returnToDefaultState**: It has been more than an hour since the user’s last interaction with the app; the app’s snapshot should return to its default state.

