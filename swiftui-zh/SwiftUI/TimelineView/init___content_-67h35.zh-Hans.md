---
来源：https://developer.apple.com/documentation/SwiftUI/TimelineView/init(_:content:)-67h35
抓取时间：2025-12-03T04:53:35Z
---

# init(_:content:)

**Initializer**

创建使用给定时间表的新时间线视图。

## 声明

```swift
nonisolated init(_ schedule: Schedule, @ViewBuilder content: @escaping (TimelineView<Schedule, Content>.Context) -> Content)
```

## 参数

- **schedule**：一个日程表，用于生成一系列日期，指明视图应何时更新。请使用符合[TimelineSchedule](../TimelineSchedule.zh-Hans.md) 的类型（如[everyMinute](../TimelineSchedule/everyMinute.zh-Hans.md)）或您定义的自定义时间线计划表。
- **content**：闭包，用于在时间表指定的时刻生成视图内容。该闭包接收[Context](Context.zh-Hans.md) 类型的输入，其中包括促使更新的时间表中的日期，以及[Cadence-swift.enum](Context/Cadence-swift_enum.zh-Hans.md) 值，视图可使用该值自定义其外观。


---
source: https://developer.apple.com/documentation/SwiftUI/TimelineView/init(_:content:)-67h35
crawled: 2025-12-03T04:53:35Z
---

# init(_:content:)

**Initializer**

Creates a new timeline view that uses the given schedule.

## Declaration

```swift
nonisolated init(_ schedule: Schedule, @ViewBuilder content: @escaping (TimelineView<Schedule, Content>.Context) -> Content)
```

## Parameters

- **schedule**: A schedule that produces a sequence of dates that indicate the instances when the view should update. Use a type that conforms to [TimelineSchedule](../TimelineSchedule.zh-Hans.md), like [everyMinute](../TimelineSchedule/everyMinute.zh-Hans.md), or a custom timeline schedule that you define.
- **content**: A closure that generates view content at the moments indicated by the schedule. The closure takes an input of type [Context](Context.zh-Hans.md) that includes the date from the schedule that prompted the update, as well as a [Cadence-swift.enum](Context/Cadence-swift_enum.zh-Hans.md) value that the view can use to customize its appearance.

