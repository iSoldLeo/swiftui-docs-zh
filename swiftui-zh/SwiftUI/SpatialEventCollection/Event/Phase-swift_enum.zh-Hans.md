---
来源： https://developer.apple.com/documentation/SwiftUI/SpatialEventCollection/Event/Phase-swift.enum
抓取时间： 2025-12-04T13:37:53Z
---

# SpatialEventCollection.Event.Phase

**Enumeration**

事件可能具有的状态。

## 声明

```swift
enum Phase
```

## 获取相位

- **SpatialEventCollection.Event.Phase.active**：该阶段处于活动状态，与之相关的状态保证至少再产生一次更新。
- **SpatialEventCollection.Event.Phase.cancelled**：与该阶段相关的状态已被取消，不会再产生任何更新。
- **SpatialEventCollection.Event.Phase.ended**：与此阶段相关的状态正常结束，不会再产生任何更新。

## 获取事件的当前阶段

- **phase**：事件的阶段。

## 符合

- 等价
- 可散列


---
source: https://developer.apple.com/documentation/SwiftUI/SpatialEventCollection/Event/Phase-swift.enum
crawled: 2025-12-04T13:37:53Z
---

# SpatialEventCollection.Event.Phase

**Enumeration**

The states that an event can have.

## Declaration

```swift
enum Phase
```

## Getting the phase

- **SpatialEventCollection.Event.Phase.active**: The phase is active and the state associated with it is guaranteed to produce at least one more update.
- **SpatialEventCollection.Event.Phase.cancelled**: The state associated with this phase was canceled and won’t produce any more updates.
- **SpatialEventCollection.Event.Phase.ended**: The state associated with this phase ended normally and won’t produce any more updates.

## Getting the event’s current phase

- **phase**: The phase of the event.

## Conforms To

- Equatable
- Hashable

