---
来源： https://developer.apple.com/documentation/SwiftUI/TimelineSchedule/everyMinute
抓取时间： 2025-12-03T06:15:33Z
---

# 每分钟

**类型属性**

每分钟开始更新时间线视图的时间表。

## 声明

```swift
static var everyMinute: EveryMinuteTimelineSchedule { get }
```

## 讨论

如果要在每分钟开始时更新时间轴视图，请使用每分钟时间轴计划初始化[TimelineView](../TimelineView.zh-Hans.md)：

```swift
TimelineView(.everyMinute) { context in
    Text(context.date.description)
}
```

时间表提供的第一个日期是您使用它初始化时间线视图的分钟开始时间。例如，如果在 `10:09:38`创建时间轴视图，计划表的第一个条目就是 `10:09:00`。对此，时间线视图会立即执行第一次更新，提供当前分钟的开始时间，即`10:09:00`，作为其内容的上下文。随后的更新将在接下来的每分钟开始时进行。

时间表定义了 [Entries](../EveryMinuteTimelineSchedule/Entries.zh-Hans.md) 结构，以便在时间线视图调用 [entries(from:mode:)](../EveryMinuteTimelineSchedule/entries_from_mode.zh-Hans.md) 方法时返回日期序列。

## 获取内置时间表

- **animation**：可暂停的日期计划表，更新频率不超过所提供的时间间隔。
- **animation(minimumInterval:paused:)**：可暂停的日期计划表，更新频率不超过所提供的间隔时间。
- **explicit(_:)**：在明确的时间点更新时间线视图的时间表。
- **periodic(from:by:)**：定期更新时间轴视图的计划。


---
source: https://developer.apple.com/documentation/SwiftUI/TimelineSchedule/everyMinute
crawled: 2025-12-03T06:15:33Z
---

# everyMinute

**Type Property**

A schedule for updating a timeline view at the start of every minute.

## Declaration

```swift
static var everyMinute: EveryMinuteTimelineSchedule { get }
```

## Discussion

Initialize a [TimelineView](../TimelineView.zh-Hans.md) with an every minute timeline schedule when you want to schedule timeline view updates at the start of every minute:

```swift
TimelineView(.everyMinute) { context in
    Text(context.date.description)
}
```

The schedule provides the first date as the beginning of the minute in which you use it to initialize the timeline view. For example, if you create the timeline view at `10:09:38`, the schedule’s first entry is `10:09:00`. In response, the timeline view performs its first update immediately, providing the beginning of the current minute, namely `10:09:00`, as context to its content. Subsequent updates happen at the beginning of each minute that follows.

The schedule defines the [Entries](../EveryMinuteTimelineSchedule/Entries.zh-Hans.md) structure to return the sequence of dates when the timeline view calls the [entries(from:mode:)](../EveryMinuteTimelineSchedule/entries_from_mode.zh-Hans.md) method.

## Getting built-in schedules

- **animation**: A pausable schedule of dates updating at a frequency no more quickly than the provided interval.
- **animation(minimumInterval:paused:)**: A pausable schedule of dates updating at a frequency no more quickly than the provided interval.
- **explicit(_:)**: A schedule for updating a timeline view at explicit points in time.
- **periodic(from:by:)**: A schedule for updating a timeline view at regular intervals.

