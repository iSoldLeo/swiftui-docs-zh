---
来源：https://developer.apple.com/documentation/SwiftUI/EveryMinuteTimelineSchedule/entries(from:mode:)
抓取时间： 2025-12-04T13:16:02Z
---

# 条目（from:mode:)

**实例方法**

提供从给定日期开始的每分钟日期序列。

## 声明

```swift
func entries(from startDate: Date, mode: TimelineScheduleMode) -> EveryMinuteTimelineSchedule.Entries
```

## 参数

- **startDate**：序列开始的日期。
- **mode**：更新计划的模式。

## 返回值

以升序排列的每分钟日期序列。

## 讨论

使用每分钟计划表创建的[TimelineView](../TimelineView.zh-Hans.md) 会调用此方法询问计划表何时更新其内容。该方法按从最早到最近的递增顺序返回每分钟日期的序列，表示时间轴视图的更新时间。

如果`startDate` 正好与分钟对齐，则计划表的日期序列从该时间开始。否则，从指定的分钟开始。例如，对于 `10:09:32` 和 `10:09:00` 的开始日期，序列中的第一个条目是 `10:09:00`。

## 获取日期序列

- **EveryMinuteTimelineSchedule.Entries**：每分钟计划表中的日期序列。


---
source: https://developer.apple.com/documentation/SwiftUI/EveryMinuteTimelineSchedule/entries(from:mode:)
crawled: 2025-12-04T13:16:02Z
---

# entries(from:mode:)

**Instance Method**

Provides a sequence of per-minute dates starting from a given date.

## Declaration

```swift
func entries(from startDate: Date, mode: TimelineScheduleMode) -> EveryMinuteTimelineSchedule.Entries
```

## Parameters

- **startDate**: The date from which the sequence begins.
- **mode**: The mode for the update schedule.

## Return Value

A sequence of per-minute dates in ascending order.

## Discussion

A [TimelineView](../TimelineView.zh-Hans.md) that you create with an every minute schedule calls this method to ask the schedule when to update its content. The method returns a sequence of per-minute dates in increasing order, from earliest to latest, that represents when the timeline view updates.

For a `startDate` that’s exactly minute-aligned, the schedule’s sequence of dates starts at that time. Otherwise, it starts at the beginning of the specified minute. For example, for start dates of both `10:09:32` and `10:09:00`, the first entry in the sequence is `10:09:00`.

## Getting the sequence of dates

- **EveryMinuteTimelineSchedule.Entries**: The sequence of dates in an every minute schedule.

