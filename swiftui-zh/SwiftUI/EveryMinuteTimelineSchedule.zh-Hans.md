--- 来源：https://developer.apple.com/documentation/SwiftUI/EveryMinuteTimelineSchedule
抓取时间：2025-12-03T06:15:40Z

---

# EveryMinuteTimelineSchedule

**Structure**

用于在每分钟开始时更新时间线视图的计划任务。

## 声明

```swift
struct EveryMinuteTimelineSchedule
```

## 概述

您也可以使用 [everyMinute](TimelineSchedule/everyMinute.zh-Hans.md) 来构建此计划任务。

## 创建计划任务

- **init()**：创建一个每分钟更新一次的计划任务。

## 获取日期序列

- **entries(from:mode:)**：提供从给定日期开始的每分钟更新日期序列。

- **EveryMinuteTimelineSchedule.Entries**：每分钟更新一次的日期序列。

## 支持的类型

- **AnimationTimelineSchedule**：可暂停的日期更新计划，更新频率不超过指定的时间间隔。

- **ExplicitTimelineSchedule**：用于在指定时间点更新时间线视图的计划。

- **PeriodicTimelineSchedule**：用于按固定时间间隔更新时间线视图的计划。

## 符合以下规范

- Sendable

- SendableMetatype

- TimelineSchedule


---
source: https://developer.apple.com/documentation/SwiftUI/EveryMinuteTimelineSchedule
crawled: 2025-12-03T06:15:40Z
---

# EveryMinuteTimelineSchedule

**Structure**

A schedule for updating a timeline view at the start of every minute.

## Declaration

```swift
struct EveryMinuteTimelineSchedule
```

## Overview

You can also use [everyMinute](TimelineSchedule/everyMinute.zh-Hans.md) to construct this schedule.

## Creating a schedule

- **init()**: Creates a per-minute update schedule.

## Getting the sequence of dates

- **entries(from:mode:)**: Provides a sequence of per-minute dates starting from a given date.
- **EveryMinuteTimelineSchedule.Entries**: The sequence of dates in an every minute schedule.

## Supporting types

- **AnimationTimelineSchedule**: A pausable schedule of dates updating at a frequency no more quickly than the provided interval.
- **ExplicitTimelineSchedule**: A schedule for updating a timeline view at explicit points in time.
- **PeriodicTimelineSchedule**: A schedule for updating a timeline view at regular intervals.

## Conforms To

- Sendable
- SendableMetatype
- TimelineSchedule

