---
来源： https://developer.apple.com/documentation/SwiftUI/EveryMinuteTimelineSchedule/Entries
抓取时间： 2025-12-04T13:16:03Z
---

# EveryMinuteTimelineSchedule.Entries

**Structure**

每分钟时间表中的日期序列。

## 声明

```swift
struct Entries
```

## 概览

[entries(from:mode:)](entries_from_mode.zh-Hans.md)方法返回该类型的值，该值是日期的[doc://com.apple.documentation/documentation/Swift/Sequence]，每分钟一个，按升序排列。您创建的[TimelineView](../TimelineView.zh-Hans.md) 在与序列中的日期相对应的时刻更新其内容。

## 获取日期序列

- **entries(from:mode:)**：提供从给定日期开始的每分钟日期序列。

## 符合

- 迭代器协议
- 可发送
- 可发送元类型
- 序列


---
source: https://developer.apple.com/documentation/SwiftUI/EveryMinuteTimelineSchedule/Entries
crawled: 2025-12-04T13:16:03Z
---

# EveryMinuteTimelineSchedule.Entries

**Structure**

The sequence of dates in an every minute schedule.

## Declaration

```swift
struct Entries
```

## Overview

The [entries(from:mode:)](entries_from_mode.zh-Hans.md) method returns a value of this type, which is a [doc://com.apple.documentation/documentation/Swift/Sequence] of dates, one per minute, in ascending order. A [TimelineView](../TimelineView.zh-Hans.md) that you create updates its content at the moments in time corresponding to the dates included in the sequence.

## Getting the sequence of dates

- **entries(from:mode:)**: Provides a sequence of per-minute dates starting from a given date.

## Conforms To

- IteratorProtocol
- Sendable
- SendableMetatype
- Sequence

