---
来源： https://developer.apple.com/documentation/SwiftUI/TimelineScheduleMode
抓取时间： 2025-12-03T06:15:38Z
---

# 时间轴计划模式

**Enumeration**

时间线计划更新的运行模式。

## 声明

```swift
enum TimelineScheduleMode
```

## 概览

当调用日程表的[entries(from:mode:)](TimelineSchedule/entries_from_mode.zh-Hans.md)方法时，[TimelineView](TimelineView.zh-Hans.md)会提供一种模式。视图根据系统状态选择模式。例如，当用户放下手腕时，watchOS 视图可能会使用 [lowFrequency](TimelineScheduleMode/lowFrequency.zh-Hans.md) 模式请求降低更新频率。

## 获取时间线计划模式

- **TimelineScheduleMode.normal**：以计划表的自然节奏更新计划表的模式。
- **TimelineScheduleMode.lowFrequency**：一种以较低速率进行计划更新的模式。

## 指定模式

- **TimelineSchedule.Mode**：时间线计划更新模式的别名。

## 符合

- 可复制
- 等价
- 可散列
- 可发送
- 可发送元类型


---
source: https://developer.apple.com/documentation/SwiftUI/TimelineScheduleMode
crawled: 2025-12-03T06:15:38Z
---

# TimelineScheduleMode

**Enumeration**

A mode of operation for timeline schedule updates.

## Declaration

```swift
enum TimelineScheduleMode
```

## Overview

A [TimelineView](TimelineView.zh-Hans.md) provides a mode when calling its schedule’s [entries(from:mode:)](TimelineSchedule/entries_from_mode.zh-Hans.md) method. The view chooses a mode based on the state of the system. For example, a watchOS view might request a lower frequency of updates, using the [lowFrequency](TimelineScheduleMode/lowFrequency.zh-Hans.md) mode, when the user lowers their wrist.

## Getting timeline schedule modes

- **TimelineScheduleMode.normal**: A mode that produces schedule updates at the schedule’s natural cadence.
- **TimelineScheduleMode.lowFrequency**: A mode that produces schedule updates at a reduced rate.

## Specifying a mode

- **TimelineSchedule.Mode**: An alias for the timeline schedule update mode.

## Conforms To

- Copyable
- Equatable
- Hashable
- Sendable
- SendableMetatype

