---
来源：https://developer.apple.com/documentation/SwiftUI/TimelineSchedule/entries(from:mode:)
抓取时间：2025-12-03T06:15:36Z
---

# 条目（from:mode:)

**实例方法**

提供从给定日期开始的日期序列。

## 声明

```swift
func entries(from startDate: Date, mode: Self.Mode) -> Self.Entries
```

## 参数

- **startDate**：序列开始的日期。
- **mode**：日程表是正常更新还是以其他节奏更新的指示。

## 返回值

升序排列的日期序列。

## 讨论

您创建的[TimelineView](../TimelineView.zh-Hans.md) 会调用此方法来确定何时更新其内容。该方法按递增顺序返回一系列日期，代表时间轴视图应该更新的时间点。符合[TimelineSchedule](../TimelineSchedule.zh-Hans.md) 协议的类型（如[periodic(from:by:)](periodic_from_by.zh-Hans.md) 返回的类型）或您定义的自定义计划表会实现此方法的自定义版本，以实现特定类型的计划表。

序列中的一个或多个日期可能早于给定的 `startDate`，在这种情况下，时间线视图会在`startDate`处使用最靠近该日期的条目执行首次更新。例如，如果响应`startDate`的`10:09:55`，方法返回的序列值为`10:09:00`、`10:10:00`、`10:11:00`，以此类推、时间轴视图会在`10:09:55` 处执行一次初始更新（使用`10:09:00` 条目），然后从`10:10:00` 开始每分钟更新一次。

符合要求的类型应尽可能根据`mode` 调整其行为。例如，为定时器提供更新的定期计划表可以在 [lowFrequency](../TimelineScheduleMode/lowFrequency.zh-Hans.md) 模式下限制每分钟更新一次：

```swift
func entries(
    from startDate: Date, mode: TimelineScheduleMode
) -> PeriodicTimelineSchedule {
    .periodic(
        from: startDate, by: (mode == .lowFrequency ? 60.0 : 1.0)
    )
}
```

## 获取日期序列

- **Entries**：计划表中的日期序列。


---
source: https://developer.apple.com/documentation/SwiftUI/TimelineSchedule/entries(from:mode:)
crawled: 2025-12-03T06:15:36Z
---

# entries(from:mode:)

**Instance Method**

Provides a sequence of dates starting around a given date.

## Declaration

```swift
func entries(from startDate: Date, mode: Self.Mode) -> Self.Entries
```

## Parameters

- **startDate**: The date by which the sequence begins.
- **mode**: An indication of whether the schedule updates normally, or with some other cadence.

## Return Value

A sequence of dates in ascending order.

## Discussion

A [TimelineView](../TimelineView.zh-Hans.md) that you create calls this method to figure out when to update its content. The method returns a sequence of dates in increasing order that represent points in time when the timeline view should update. Types that conform to the [TimelineSchedule](../TimelineSchedule.zh-Hans.md) protocol, like the one returned by [periodic(from:by:)](periodic_from_by.zh-Hans.md), or a custom schedule that you define, implement a custom version of this method to implement a particular kind of schedule.

One or more dates in the sequence might be before the given `startDate`, in which case the timeline view performs its first update at `startDate` using the entry that most closely precedes that date. For example, if in response to a `startDate` of `10:09:55`, the method returns a sequence with the values `10:09:00`, `10:10:00`, `10:11:00`, and so on, the timeline view performs an initial update at `10:09:55` (using the `10:09:00` entry), followed by another update at the beginning of every minute, starting at `10:10:00`.

A type that conforms should adjust its behavior based on the `mode` when possible. For example, a periodic schedule providing updates for a timer could restrict updates to once per minute while in the [lowFrequency](../TimelineScheduleMode/lowFrequency.zh-Hans.md) mode:

```swift
func entries(
    from startDate: Date, mode: TimelineScheduleMode
) -> PeriodicTimelineSchedule {
    .periodic(
        from: startDate, by: (mode == .lowFrequency ? 60.0 : 1.0)
    )
}
```

## Getting a sequence of dates

- **Entries**: The sequence of dates within a schedule.

