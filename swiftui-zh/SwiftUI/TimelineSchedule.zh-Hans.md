--- 来源：https://developer.apple.com/documentation/SwiftUI/TimelineSchedule
抓取时间：2025-12-02T17:34:13Z

---

# TimelineSchedule

**Protocol**

一种提供日期序列的类型，可用作日程安排。

## 声明

```swift
protocol TimelineSchedule
```

## 概述

遵循此协议的类型通过定义一个返回日期序列的 [entries(from:mode:)](TimelineSchedule/entries_from_mode.zh-Hans.md) 方法来实现特定类型的日程安排。初始化 [TimelineView](TimelineView.zh-Hans.md) 时，请使用时间线日程安排类型。例如，您可以创建一个时间线视图，该视图从某个日期 `startDate` 开始，每秒更新一次，使用由 [periodic(from:by:)](TimelineSchedule/periodic_from_by.zh-Hans.md) 返回的周期性计划：

```swift
TimelineView(.periodic(from: startDate, by: 1.0)) { context in
    // View content goes here.
}
```

您还可以创建自定义时间线计划。时间线视图会根据计划生成的日期序列更新其内容。

## 获取内置计划

- **animation**：一个可暂停的日期更新计划，其更新频率不会超过指定的时间间隔。

- **animation(minimumInterval:paused:)**：一个可暂停的日期更新计划，其更新频率不会超过指定的时间间隔。

- **everyMinute**：一个在每分钟开始时更新时间线视图的计划。

- **explicit(_:)**：一个在指定时间点更新时间线视图的计划。

- **periodic(from:by:)**：用于定期更新时间线视图的计划任务。

## 获取日期序列

- **entries(from:mode:)**：提供从给定日期附近开始的日期序列。

- **Entries**：计划任务中的日期序列。

## 指定模式

- **TimelineSchedule.Mode**：时间线计划任务更新模式的别名。

- **TimelineScheduleMode**：时间线计划任务更新的操作模式。

## 支持的类型

- **AnimationTimelineSchedule**：可暂停的日期计划任务，其更新频率不高于指定的间隔。

- **EveryMinuteTimelineSchedule**：用于每分钟开始时更新时间线视图的计划任务。

- **ExplicitTimelineSchedule**：用于在指定时间点更新时间线视图的计划表。

- **PeriodicTimelineSchedule**：用于按固定时间间隔更新时间线视图的计划表。

## 按计划更新视图

- **使用时间线更新 watchOS 应用**：即使用户界面处于非活动状态，也能无缝地安排更新。

- **TimelineView**：根据您提供的计划表更新的视图。

- **TimelineViewDefaultContext**：传递给时间线视图内容回调的信息。

## 符合规范的类型

- AnimationTimelineSchedule

- EveryMinuteTimelineSchedule

- ExplicitTimelineSchedule

- PeriodicTimelineSchedule


---
source: https://developer.apple.com/documentation/SwiftUI/TimelineSchedule
crawled: 2025-12-02T17:34:13Z
---

# TimelineSchedule

**Protocol**

A type that provides a sequence of dates for use as a schedule.

## Declaration

```swift
protocol TimelineSchedule
```

## Overview

Types that conform to this protocol implement a particular kind of schedule by defining an [entries(from:mode:)](TimelineSchedule/entries_from_mode.zh-Hans.md) method that returns a sequence of dates. Use a timeline schedule type when you initialize a [TimelineView](TimelineView.zh-Hans.md). For example, you can create a timeline view that updates every second, starting from some `startDate`, using a periodic schedule returned by [periodic(from:by:)](TimelineSchedule/periodic_from_by.zh-Hans.md):

```swift
TimelineView(.periodic(from: startDate, by: 1.0)) { context in
    // View content goes here.
}
```

You can also create custom timeline schedules. The timeline view updates its content according to the sequence of dates produced by the schedule.

## Getting built-in schedules

- **animation**: A pausable schedule of dates updating at a frequency no more quickly than the provided interval.
- **animation(minimumInterval:paused:)**: A pausable schedule of dates updating at a frequency no more quickly than the provided interval.
- **everyMinute**: A schedule for updating a timeline view at the start of every minute.
- **explicit(_:)**: A schedule for updating a timeline view at explicit points in time.
- **periodic(from:by:)**: A schedule for updating a timeline view at regular intervals.

## Getting a sequence of dates

- **entries(from:mode:)**: Provides a sequence of dates starting around a given date.
- **Entries**: The sequence of dates within a schedule.

## Specifying a mode

- **TimelineSchedule.Mode**: An alias for the timeline schedule update mode.
- **TimelineScheduleMode**: A mode of operation for timeline schedule updates.

## Supporting types

- **AnimationTimelineSchedule**: A pausable schedule of dates updating at a frequency no more quickly than the provided interval.
- **EveryMinuteTimelineSchedule**: A schedule for updating a timeline view at the start of every minute.
- **ExplicitTimelineSchedule**: A schedule for updating a timeline view at explicit points in time.
- **PeriodicTimelineSchedule**: A schedule for updating a timeline view at regular intervals.

## Updating a view on a schedule

- **Updating watchOS apps with timelines**: Seamlessly schedule updates to your user interface, even while it’s inactive.
- **TimelineView**: A view that updates according to a schedule that you provide.
- **TimelineViewDefaultContext**: Information passed to a timeline view’s content callback.

## Conforming Types

- AnimationTimelineSchedule
- EveryMinuteTimelineSchedule
- ExplicitTimelineSchedule
- PeriodicTimelineSchedule

