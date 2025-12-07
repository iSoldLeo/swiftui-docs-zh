---
来源：https://developer.apple.com/documentation/SwiftUI/AnimationTimelineSchedule/init(minimumInterval:paused:)
抓取时间：2025-12-04T13:16:00Z
---

# init(minimumInterval:paused:)

**Initializer**

创建一个可暂停的日期计划表，更新频率不超过提供的间隔时间。

## 声明

```swift
init(minimumInterval: Double? = nil, paused: Bool = false)
```

## 参数

- **minimumInterval**：更新计划表的最小间隔。通过 nil 可让系统选择一个合适的更新间隔。
- **paused**：计划表是否应停止生成更新。


---
source: https://developer.apple.com/documentation/SwiftUI/AnimationTimelineSchedule/init(minimumInterval:paused:)
crawled: 2025-12-04T13:16:00Z
---

# init(minimumInterval:paused:)

**Initializer**

Create a pausable schedule of dates updating at a frequency no more quickly than the provided interval.

## Declaration

```swift
init(minimumInterval: Double? = nil, paused: Bool = false)
```

## Parameters

- **minimumInterval**: The minimum interval to update the schedule at. Pass nil to let the system pick an appropriate update interval.
- **paused**: If the schedule should stop generating updates.

