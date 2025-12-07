---
来源： https://developer.apple.com/documentation/SwiftUI/TimelineSchedule/animation
抓取时间： 2025-12-03T06:15:32Z
---

# 动画

**类型属性**

可暂停的日期时间表，更新频率不超过所提供的时间间隔。

## 声明

```swift
static var animation: AnimationTimelineSchedule { get }
```

## 获取内置时间表

- **animation(minimumInterval:paused:)**：可暂停的日期计划表，更新频率不超过所提供的间隔时间。
- **everyMinute**：每分钟开始更新时间线视图的计划表。
- **explicit(_:)**：在明确的时间点更新时间轴视图的计划。
- **periodic(from:by:)**：定期更新时间线视图的计划。


---
source: https://developer.apple.com/documentation/SwiftUI/TimelineSchedule/animation
crawled: 2025-12-03T06:15:32Z
---

# animation

**Type Property**

A pausable schedule of dates updating at a frequency no more quickly than the provided interval.

## Declaration

```swift
static var animation: AnimationTimelineSchedule { get }
```

## Getting built-in schedules

- **animation(minimumInterval:paused:)**: A pausable schedule of dates updating at a frequency no more quickly than the provided interval.
- **everyMinute**: A schedule for updating a timeline view at the start of every minute.
- **explicit(_:)**: A schedule for updating a timeline view at explicit points in time.
- **periodic(from:by:)**: A schedule for updating a timeline view at regular intervals.

