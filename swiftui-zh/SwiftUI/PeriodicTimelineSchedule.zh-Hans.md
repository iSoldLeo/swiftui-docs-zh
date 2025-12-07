--- 来源：https://developer.apple.com/documentation/SwiftUI/PeriodicTimelineSchedule
抓取时间：2025-12-03T06:15:42Z

---

# PeriodicTimelineSchedule

**Structure**

用于定期更新时间线视图的计划任务。

## 声明

```swift
struct PeriodicTimelineSchedule
```

## 概述

您也可以使用 [periodic(from:by:)](TimelineSchedule/periodic_from_by.zh-Hans.md) 来构建此计划任务。

## 创建计划任务

- **init(from:by:)**：创建周期性更新计划任务。

## 获取日期序列

- **entries(from:mode:)**：提供从给定日期附近开始的周期性日期序列。

- **PeriodicTimelineSchedule.Entries**：周期性计划任务中的日期序列。

## 支持的类型

- **AnimationTimelineSchedule**：可暂停的日期更新计划，更新频率不高于指定的间隔。

- **EveryMinuteTimelineSchedule**：每分钟开始时更新时间线视图的计划。

- **ExplicitTimelineSchedule**：在指定时间点更新时间线视图的计划。

## 符合以下规范

- Sendable

- SendableMetatype

- TimelineSchedule


---
source: https://developer.apple.com/documentation/SwiftUI/PeriodicTimelineSchedule
crawled: 2025-12-03T06:15:42Z
---

# PeriodicTimelineSchedule

**Structure**

A schedule for updating a timeline view at regular intervals.

## Declaration

```swift
struct PeriodicTimelineSchedule
```

## Overview

You can also use [periodic(from:by:)](TimelineSchedule/periodic_from_by.zh-Hans.md) to construct this schedule.

## Creating a schedule

- **init(from:by:)**: Creates a periodic update schedule.

## Getting the sequence of dates

- **entries(from:mode:)**: Provides a sequence of periodic dates starting from around a given date.
- **PeriodicTimelineSchedule.Entries**: The sequence of dates in periodic schedule.

## Supporting types

- **AnimationTimelineSchedule**: A pausable schedule of dates updating at a frequency no more quickly than the provided interval.
- **EveryMinuteTimelineSchedule**: A schedule for updating a timeline view at the start of every minute.
- **ExplicitTimelineSchedule**: A schedule for updating a timeline view at explicit points in time.

## Conforms To

- Sendable
- SendableMetatype
- TimelineSchedule

