---
来源： https://developer.apple.com/documentation/SwiftUI/SpatialEventCollection/Event/Phase-swift.enum/ended
抓取时间： 2025-12-05T22:29:27Z
---

# SpatialEventCollection.Event.Phase.ended

**Case**

与此阶段相关的状态正常结束，不会再产生任何更新。

## 声明

```swift
case ended
```

## 获取相位

- **SpatialEventCollection.Event.Phase.active**：该阶段处于活动状态，与之相关的状态保证至少再产生一次更新。
- **SpatialEventCollection.Event.Phase.cancelled**：与该阶段相关的状态已被取消，不会再产生任何更新。


---
source: https://developer.apple.com/documentation/SwiftUI/SpatialEventCollection/Event/Phase-swift.enum/ended
crawled: 2025-12-05T22:29:27Z
---

# SpatialEventCollection.Event.Phase.ended

**Case**

The state associated with this phase ended normally and won’t produce any more updates.

## Declaration

```swift
case ended
```

## Getting the phase

- **SpatialEventCollection.Event.Phase.active**: The phase is active and the state associated with it is guaranteed to produce at least one more update.
- **SpatialEventCollection.Event.Phase.cancelled**: The state associated with this phase was canceled and won’t produce any more updates.

