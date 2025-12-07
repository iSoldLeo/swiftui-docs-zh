---
来源：https://developer.apple.com/documentation/SwiftUI/TimelineSchedule/animation(minimumInterval:paused:)
抓取时间： 2025-12-01T11:04:43Z
---

# animation(minimumInterval:paused:)

**类型方法**

一个可暂停的日期时间表，更新频率不超过所提供的时间间隔。

## 声明

```swift
static func animation(minimumInterval: Double? = nil, paused: Bool = false) -> AnimationTimelineSchedule
```

## 参数

- **minimumInterval**：更新计划表的最小间隔。通过 nil 可让系统选择一个合适的更新间隔。
- **paused**：计划表是否应停止生成更新。

## 获取内置计划表

- **animation**：可暂停的日期计划表，更新频率不超过所提供的间隔时间。
- **everyMinute**：每分钟开始更新时间线视图的计划表。
- **explicit(_:)**：在明确的时间点更新时间轴视图的计划。
- **periodic(from:by:)**：定期更新时间线视图的计划。


---
source: https://developer.apple.com/documentation/SwiftUI/TimelineSchedule/animation(minimumInterval:paused:)
crawled: 2025-12-01T11:04:43Z
---

# animation(minimumInterval:paused:)

**Type Method**

A pausable schedule of dates updating at a frequency no more quickly than the provided interval.

## Declaration

```swift
static func animation(minimumInterval: Double? = nil, paused: Bool = false) -> AnimationTimelineSchedule
```

## Parameters

- **minimumInterval**: The minimum interval to update the schedule at. Pass nil to let the system pick an appropriate update interval.
- **paused**: If the schedule should stop generating updates.

## Getting built-in schedules

- **animation**: A pausable schedule of dates updating at a frequency no more quickly than the provided interval.
- **everyMinute**: A schedule for updating a timeline view at the start of every minute.
- **explicit(_:)**: A schedule for updating a timeline view at explicit points in time.
- **periodic(from:by:)**: A schedule for updating a timeline view at regular intervals.

