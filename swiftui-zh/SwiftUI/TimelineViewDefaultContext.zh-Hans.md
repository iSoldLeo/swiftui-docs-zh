--- 来源：https://developer.apple.com/documentation/SwiftUI/TimelineViewDefaultContext
抓取时间：2025-12-02T17:34:15Z

---

# TimelineViewDefaultContext

**类型别名**

传递给时间线视图内容回调的信息。

## 声明

```swift
typealias TimelineViewDefaultContext = TimelineView<EveryMinuteTimelineSchedule, Never>.Context
```

## 讨论

上下文包含触发回调的日程日期，以及可用于自定义视图外观的节奏。例如，您可以选择仅在节奏为 [seconds](TimelineView/Context/Cadence-swift_enum/seconds.zh-Hans.md) 或更快时才显示模拟时钟的秒针。

## 按计划更新视图

- **使用时间线更新 watchOS 应用**：即使用户界面处于非活动状态，也能无缝安排更新。

- **TimelineView**：根据您提供的计划表更新的视图。

- **TimelineSchedule**：提供一系列日期作为计划表的类型。


---
source: https://developer.apple.com/documentation/SwiftUI/TimelineViewDefaultContext
crawled: 2025-12-02T17:34:15Z
---

# TimelineViewDefaultContext

**Type Alias**

Information passed to a timeline view’s content callback.

## Declaration

```swift
typealias TimelineViewDefaultContext = TimelineView<EveryMinuteTimelineSchedule, Never>.Context
```

## Discussion

The context includes both the date from the schedule that triggered the callback, and a cadence that you can use to customize the appearance of your view. For example, you might choose to display the second hand of an analog clock only when the cadence is [seconds](TimelineView/Context/Cadence-swift_enum/seconds.zh-Hans.md) or faster.



## Updating a view on a schedule

- **Updating watchOS apps with timelines**: Seamlessly schedule updates to your user interface, even while it’s inactive.
- **TimelineView**: A view that updates according to a schedule that you provide.
- **TimelineSchedule**: A type that provides a sequence of dates for use as a schedule.

