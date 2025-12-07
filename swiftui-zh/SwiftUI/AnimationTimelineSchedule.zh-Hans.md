---
来源： https://developer.apple.com/documentation/SwiftUI/AnimationTimelineSchedule
抓取时间： 2025-12-03T06:15:39Z
---

# 动画时间表

**Structure**

可暂停的日期时间表，更新频率不超过所提供的时间间隔。

## 声明

```swift
struct AnimationTimelineSchedule
```

## 概览

您也可以使用 [animation(minimumInterval:paused:)](TimelineSchedule/animation_minimumInterval_paused.zh-Hans.md) 构建此计划表。

## 创建计划表

- **init(minimumInterval:paused:)**：创建一个可暂停的日期计划表，更新频率不超过所提供的间隔时间。

## 获取日期序列

- **entries(from:mode:)**：按动画时间表的频率返回条目。

## 支持类型

- **EveryMinuteTimelineSchedule**：用于在每分钟开始时更新时间线视图的时间表。
- **ExplicitTimelineSchedule**：在明确的时间点更新时间轴视图的计划。
- **PeriodicTimelineSchedule**：定期更新时间轴视图的计划。

## 符合

- 可发送
- 可发送元类型
- 时间表


---
source: https://developer.apple.com/documentation/SwiftUI/AnimationTimelineSchedule
crawled: 2025-12-03T06:15:39Z
---

# AnimationTimelineSchedule

**Structure**

A pausable schedule of dates updating at a frequency no more quickly than the provided interval.

## Declaration

```swift
struct AnimationTimelineSchedule
```

## Overview

You can also use [animation(minimumInterval:paused:)](TimelineSchedule/animation_minimumInterval_paused.zh-Hans.md) to construct this schedule.

## Creating a schedule

- **init(minimumInterval:paused:)**: Create a pausable schedule of dates updating at a frequency no more quickly than the provided interval.

## Getting the sequence of dates

- **entries(from:mode:)**: Returns entries at the frequency of the animation schedule.

## Supporting types

- **EveryMinuteTimelineSchedule**: A schedule for updating a timeline view at the start of every minute.
- **ExplicitTimelineSchedule**: A schedule for updating a timeline view at explicit points in time.
- **PeriodicTimelineSchedule**: A schedule for updating a timeline view at regular intervals.

## Conforms To

- Sendable
- SendableMetatype
- TimelineSchedule

