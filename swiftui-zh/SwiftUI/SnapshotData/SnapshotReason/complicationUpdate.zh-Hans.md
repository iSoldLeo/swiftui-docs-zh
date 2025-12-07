--- 来源：https://developer.apple.com/documentation/SwiftUI/SnapshotData/SnapshotReason/complicationUpdate
抓取时间：2025-12-04T13:39:40Z

---

# SnapshotData.SnapshotReason.complicationUpdate

**Case**

应用更新了复杂功能时间线。

## 声明

```swift
case complicationUpdate
```

## 获取快照原因

- **SnapshotData.SnapshotReason.appBackgrounded**：应用从前台切换到后台。

- **SnapshotData.SnapshotReason.appScheduled**：应用已安排此快照。

- **SnapshotData.SnapshotReason.prelaunch**：系统需要 Dock 栏的快照，但应用尚未启动。

- **SnapshotData.SnapshotReason.returnToDefaultState**：用户上次与应用交互已超过一小时；应用的快照应恢复到默认状态。


---
source: https://developer.apple.com/documentation/SwiftUI/SnapshotData/SnapshotReason/complicationUpdate
crawled: 2025-12-04T13:39:40Z
---

# SnapshotData.SnapshotReason.complicationUpdate

**Case**

The app updated the complication timeline.

## Declaration

```swift
case complicationUpdate
```

## Getting the snapshot reasons

- **SnapshotData.SnapshotReason.appBackgrounded**: The app transitioned from the foreground to the background.
- **SnapshotData.SnapshotReason.appScheduled**: The app scheduled this snapshot.
- **SnapshotData.SnapshotReason.prelaunch**: The system needs a snapshot for the dock, but the app has not been launched yet.
- **SnapshotData.SnapshotReason.returnToDefaultState**: It has been more than an hour since the user’s last interaction with the app; the app’s snapshot should return to its default state.

