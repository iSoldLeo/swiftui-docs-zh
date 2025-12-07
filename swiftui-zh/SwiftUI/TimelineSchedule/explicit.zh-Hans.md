---
来源： https://developer.apple.com/documentation/SwiftUI/TimelineSchedule/explicit(_:)
抓取时间： 2025-12-03T06:15:34Z
---

# explicit(_:)

**类型方法**

用于在明确时间点更新时间线视图的计划。

## 声明

```swift
static func explicit<S>(_ dates: S) -> ExplicitTimelineSchedule<S> where Self == ExplicitTimelineSchedule<S>, S : Sequence, S.Element == Date
```

## 参数

- **dates**：时间轴视图更新的日期序列。使用单调递增的日期序列，并确保至少有一个日期在未来。

##讨论

如果要在特定时间点安排视图更新，请使用显式时间轴计划初始化[TimelineView](../TimelineView.zh-Hans.md)：

```swift
let dates = [
    Date(timeIntervalSinceNow: 10), // Update ten seconds from now,
    Date(timeIntervalSinceNow: 12) // and a few seconds later.
]

struct MyView: View {
    var body: some View {
        TimelineView(.explicit(dates)) { context in
            Text(context.date.description)
        }
    }
}
```

时间轴视图会按照您指定的日期更新内容，直到日期用完，之后就会停止更改。如果您提供的日期是过去的，时间轴视图会准确地更新一次最后的条目。如果只提供未来的日期，时间线视图将以当前日期渲染，直到第一个日期到来。如果您提供了一个或多个过去日期和一个或多个未来日期，则视图会显示最近的过去日期，并正常刷新所有后续日期。

## 获取内置时间表

- **animation**：可暂停的日期时间表，更新频率不超过所提供的时间间隔。
- **animation(minimumInterval:paused:)**：可暂停的日期计划表，其更新频率不超过所提供的间隔时间。
- **everyMinute**：每分钟开始更新时间线视图的计划表。
- **periodic(from:by:)**：定期更新时间轴视图的计划。


---
source: https://developer.apple.com/documentation/SwiftUI/TimelineSchedule/explicit(_:)
crawled: 2025-12-03T06:15:34Z
---

# explicit(_:)

**Type Method**

A schedule for updating a timeline view at explicit points in time.

## Declaration

```swift
static func explicit<S>(_ dates: S) -> ExplicitTimelineSchedule<S> where Self == ExplicitTimelineSchedule<S>, S : Sequence, S.Element == Date
```

## Parameters

- **dates**: The sequence of dates at which a timeline view updates. Use a monotonically increasing sequence of dates, and ensure that at least one is in the future.

## Discussion

Initialize a [TimelineView](../TimelineView.zh-Hans.md) with an explicit timeline schedule when you want to schedule view updates at particular points in time:

```swift
let dates = [
    Date(timeIntervalSinceNow: 10), // Update ten seconds from now,
    Date(timeIntervalSinceNow: 12) // and a few seconds later.
]

struct MyView: View {
    var body: some View {
        TimelineView(.explicit(dates)) { context in
            Text(context.date.description)
        }
    }
}
```

The timeline view updates its content on exactly the dates that you specify, until it runs out of dates, after which it stops changing. If the dates you provide are in the past, the timeline view updates exactly once with the last entry. If you only provide dates in the future, the timeline view renders with the current date until the first date arrives. If you provide one or more dates in the past and one or more in the future, the view renders the most recent past date, refreshing normally on all subsequent dates.

## Getting built-in schedules

- **animation**: A pausable schedule of dates updating at a frequency no more quickly than the provided interval.
- **animation(minimumInterval:paused:)**: A pausable schedule of dates updating at a frequency no more quickly than the provided interval.
- **everyMinute**: A schedule for updating a timeline view at the start of every minute.
- **periodic(from:by:)**: A schedule for updating a timeline view at regular intervals.

