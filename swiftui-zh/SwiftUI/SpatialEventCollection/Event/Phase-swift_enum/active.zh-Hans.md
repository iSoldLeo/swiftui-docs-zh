---
来源： https://developer.apple.com/documentation/SwiftUI/SpatialEventCollection/Event/Phase-swift.enum/active
抓取时间： 2025-12-05T22:29:26Z
---

# SpatialEventCollection.Event.Phase.active

**Case**

该阶段处于活动状态，与之相关的状态保证至少再产生一次更新。

## 声明

```swift
case active
```

## 获取相位

- **SpatialEventCollection.Event.Phase.cancelled**：与此阶段相关的状态已被取消，不会再产生任何更新。
- **SpatialEventCollection.Event.Phase.ended**：与此阶段相关的状态正常结束，不会再产生任何更新。


---
source: https://developer.apple.com/documentation/SwiftUI/SpatialEventCollection/Event/Phase-swift.enum/active
crawled: 2025-12-05T22:29:26Z
---

# SpatialEventCollection.Event.Phase.active

**Case**

The phase is active and the state associated with it is guaranteed to produce at least one more update.

## Declaration

```swift
case active
```

## Getting the phase

- **SpatialEventCollection.Event.Phase.cancelled**: The state associated with this phase was canceled and won’t produce any more updates.
- **SpatialEventCollection.Event.Phase.ended**: The state associated with this phase ended normally and won’t produce any more updates.

