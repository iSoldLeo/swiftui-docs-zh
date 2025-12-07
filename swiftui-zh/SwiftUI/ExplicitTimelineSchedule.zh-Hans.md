--- 来源：https://developer.apple.com/documentation/SwiftUI/ExplicitTimelineSchedule
抓取时间：2025-12-03T06:15:41Z

---

# ExplicitTimelineSchedule

**Structure**

用于在指定时间点更新时间线视图的计划任务。

## 声明

```swift
struct ExplicitTimelineSchedule<Entries> where Entries : Sequence, Entries.Element == Date
```

## 概述

您也可以使用 [explicit(_:)](TimelineSchedule/explicit.zh-Hans.md) 来构建此计划任务。

## 创建计划任务

- **init(_:)**：创建一个由指定日期序列组成的计划任务。

## 获取日期序列

- **entries(from:mode:)**：提供您初始化计划任务时使用的日期序列。

## 支持的类型

- **AnimationTimelineSchedule**：可暂停的日期更新计划，更新频率不高于指定的间隔。

- **EveryMinuteTimelineSchedule**：每分钟开始时更新时间线视图的计划。

- **PeriodicTimelineSchedule**：定期更新时间线视图的计划。

## 符合以下规范

- TimelineSchedule


---
source: https://developer.apple.com/documentation/SwiftUI/ExplicitTimelineSchedule
crawled: 2025-12-03T06:15:41Z
---

# ExplicitTimelineSchedule

**Structure**

A schedule for updating a timeline view at explicit points in time.

## Declaration

```swift
struct ExplicitTimelineSchedule<Entries> where Entries : Sequence, Entries.Element == Date
```

## Overview

You can also use [explicit(_:)](TimelineSchedule/explicit.zh-Hans.md) to construct this schedule.

## Creating a schedule

- **init(_:)**: Creates a schedule composed of an explicit sequence of dates.

## Getting the sequence of dates

- **entries(from:mode:)**: Provides the sequence of dates with which you initialized the schedule.

## Supporting types

- **AnimationTimelineSchedule**: A pausable schedule of dates updating at a frequency no more quickly than the provided interval.
- **EveryMinuteTimelineSchedule**: A schedule for updating a timeline view at the start of every minute.
- **PeriodicTimelineSchedule**: A schedule for updating a timeline view at regular intervals.

## Conforms To

- TimelineSchedule

