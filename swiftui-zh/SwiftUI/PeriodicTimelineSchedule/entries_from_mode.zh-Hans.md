--- 来源：https://developer.apple.com/documentation/SwiftUI/PeriodicTimelineSchedule/entries(from:mode:)

抓取时间：2025-12-04T13:16:06Z

---

# entries(from:mode:)

**实例方法**

提供从给定日期附近开始的周期性日期序列。

## 声明

```swift
func entries(from startDate: Date, mode: TimelineScheduleMode) -> PeriodicTimelineSchedule.Entries
```

## 说明

您使用日程表创建的 [TimelineView](../TimelineView.zh-Hans.md) 会调用此方法来询问日程表何时更新其内容。该方法返回一个按递增顺序排列的等间隔日期序列，这些日期表示时间线视图应该更新的时间点。

日程表根据您传递给其 [init(from:by:)](init_from_by.zh-Hans.md) 初始化器的参数定义其周期性和相位对齐方式。例如，对于 `startDate` 和 `interval` 分别为 `10:09:30` 和 `60` 秒的情况，日程安排会在每分钟的半点发布日期。传递给 `entries(from:mode:)` 方法的 `startDate` 则决定了序列中的第一个日期，即起始日期所覆盖的时间间隔的开始。继续上面的例子，起始日期为 `10:34:45` 会导致序列中的第一个条目为 `10:34:30`，因为这是起始日期所在的时间间隔的开始。

## 获取日期序列

- **PeriodicTimelineSchedule.Entries**：周期性日程安排中的日期序列。


---
source: https://developer.apple.com/documentation/SwiftUI/PeriodicTimelineSchedule/entries(from:mode:)
crawled: 2025-12-04T13:16:06Z
---

# entries(from:mode:)

**Instance Method**

Provides a sequence of periodic dates starting from around a given date.

## Declaration

```swift
func entries(from startDate: Date, mode: TimelineScheduleMode) -> PeriodicTimelineSchedule.Entries
```

## Discussion

A [TimelineView](../TimelineView.zh-Hans.md) that you create with a schedule calls this method to ask the schedule when to update its content. The method returns a sequence of equally spaced dates in increasing order that represent points in time when the timeline view should update.

The schedule defines its periodicity and phase aligment based on the parameters you pass to its [init(from:by:)](init_from_by.zh-Hans.md) initializer. For example, for a `startDate` and `interval` of `10:09:30` and `60` seconds, the schedule prepares to issue dates half past each minute. The `startDate` that you pass to the `entries(from:mode:)` method then dictates the first date of the sequence as the beginning of the interval that the start date overlaps. Continuing the example above, a start date of `10:34:45` causes the first sequence entry to be `10:34:30`, because that’s the start of the interval in which the start date appears.

## Getting the sequence of dates

- **PeriodicTimelineSchedule.Entries**: The sequence of dates in periodic schedule.

