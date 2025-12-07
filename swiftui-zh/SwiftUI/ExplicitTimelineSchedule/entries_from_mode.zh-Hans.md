---
来源：https://developer.apple.com/documentation/SwiftUI/ExplicitTimelineSchedule/entries(from:mode:)
抓取时间：2025-12-04T13:16:04Z
---

# 条目（from:mode:)

**实例方法**

提供用于初始化计划表的日期序列。

## 声明

```swift
func entries(from startDate: Date, mode: TimelineScheduleMode) -> Entries
```

## 参数

- **startDate**：序列开始的日期。本协议方法的特定实现忽略起始日期。
- **mode**：更新时间表的模式。本协议方法的特定实现方式忽略该模式。

## 返回值

初始化时提供的日期序列。

## 讨论

使用计划表创建的 [TimelineView](../TimelineView.zh-Hans.md) 会调用此 [TimelineSchedule](../TimelineSchedule.zh-Hans.md) 方法来询问计划表何时更新其内容。此方法的显式时间线计划表实现返回的是在用[explicit(_:)](../TimelineSchedule/explicit.zh-Hans.md) 创建计划表时提供的未经修改的日期序列。因此，此特定实现会忽略 `startDate` 和 `mode` 参数。


---
source: https://developer.apple.com/documentation/SwiftUI/ExplicitTimelineSchedule/entries(from:mode:)
crawled: 2025-12-04T13:16:04Z
---

# entries(from:mode:)

**Instance Method**

Provides the sequence of dates with which you initialized the schedule.

## Declaration

```swift
func entries(from startDate: Date, mode: TimelineScheduleMode) -> Entries
```

## Parameters

- **startDate**: The date from which the sequence begins. This particular implementation of the protocol method ignores the start date.
- **mode**: The mode for the update schedule. This particular implementation of the protocol method ignores the mode.

## Return Value

The sequence of dates that you provided at initialization.

## Discussion

A [TimelineView](../TimelineView.zh-Hans.md) that you create with a schedule calls this [TimelineSchedule](../TimelineSchedule.zh-Hans.md) method to ask the schedule when to update its content. The explicit timeline schedule implementation of this method returns the unmodified sequence of dates that you provided when you created the schedule with [explicit(_:)](../TimelineSchedule/explicit.zh-Hans.md). As a result, this particular implementation ignores the `startDate` and `mode` parameters.

