---
来源：https://developer.apple.com/documentation/SwiftUI/TimelineSchedule/periodic(from:by:)
抓取时间：2025-12-01T11:04:46Z
---

# periodic(from:by:)

**类型方法**

定期更新时间线视图的计划。

## 声明

```swift
static func periodic(from startDate: Date, by interval: TimeInterval) -> PeriodicTimelineSchedule
```

## 参数

- **startDate**：开始序列的日期。
- **interval**：连续序列条目之间的时间间隔。

### 讨论

当您想以自定义时间间隔定期更新时间轴视图时，请使用周期性时间轴计划初始化⟦DL_0005ɷ：

```swift
TimelineView(.periodic(from: startDate, by: 3.0)) { context in
    Text(context.date.description)
}
```

时间线视图会在开始日期更新内容，然后在时间间隔量（上例中为每三秒一次）相隔的日期再次更新内容。对于过去的开始日期，视图会立即更新，并提供与最近的时间间隔边界相对应的日期作为上下文。然后，视图会在随后的时间间隔边界正常刷新。对于未来的起始日期，视图更新一次当前日期，然后开始定期更新起始日期。

时间表定义了 [Entries](../PeriodicTimelineSchedule/Entries.zh-Hans.md) 结构，用于在时间线视图调用 [entries(from:mode:)](../PeriodicTimelineSchedule/entries_from_mode.zh-Hans.md) 方法时返回日期序列。

## 获取内置时间表

- **animation**：可暂停的日期计划表，更新频率不超过所提供的时间间隔。
- **animation(minimumInterval:paused:)**：可暂停的日期计划表，更新频率不超过所提供的间隔时间。
- **everyMinute**：每分钟开始更新时间线视图的计划表。
- **explicit(_:)**：在明确的时间点更新时间线视图的计划。


---
source: https://developer.apple.com/documentation/SwiftUI/TimelineSchedule/periodic(from:by:)
crawled: 2025-12-01T11:04:46Z
---

# periodic(from:by:)

**Type Method**

A schedule for updating a timeline view at regular intervals.

## Declaration

```swift
static func periodic(from startDate: Date, by interval: TimeInterval) -> PeriodicTimelineSchedule
```

## Parameters

- **startDate**: The date on which to start the sequence.
- **interval**: The time interval between successive sequence entries.

## Discussion

Initialize a [TimelineView](../TimelineView.zh-Hans.md) with a periodic timeline schedule when you want to schedule timeline view updates periodically with a custom interval:

```swift
TimelineView(.periodic(from: startDate, by: 3.0)) { context in
    Text(context.date.description)
}
```

The timeline view updates its content at the start date, and then again at dates separated in time by the interval amount, which is every three seconds in the example above. For a start date in the past, the view updates immediately, providing as context the date corresponding to the most recent interval boundary. The view then refreshes normally at subsequent interval boundaries. For a start date in the future, the view updates once with the current date, and then begins regular updates at the start date.

The schedule defines the [Entries](../PeriodicTimelineSchedule/Entries.zh-Hans.md) structure to return the sequence of dates when the timeline view calls the [entries(from:mode:)](../PeriodicTimelineSchedule/entries_from_mode.zh-Hans.md) method.

## Getting built-in schedules

- **animation**: A pausable schedule of dates updating at a frequency no more quickly than the provided interval.
- **animation(minimumInterval:paused:)**: A pausable schedule of dates updating at a frequency no more quickly than the provided interval.
- **everyMinute**: A schedule for updating a timeline view at the start of every minute.
- **explicit(_:)**: A schedule for updating a timeline view at explicit points in time.

