--- 来源：https://developer.apple.com/documentation/SwiftUI/PeriodicTimelineSchedule/Entries

抓取时间：2025-12-04T13:16:06Z

---

# PeriodicTimelineSchedule.Entries

**Structure**

周期性日程表中的日期序列。

## 声明

```swift
struct Entries
```

## 概述

[entries(from:mode:)](entries_from_mode.zh-Hans.md) 方法返回此类型的值，该值是一个按升序排列的周期性日期序列。[doc://com.apple.documentation/documentation/Swift/Sequence] 您创建的 [TimelineView](../TimelineView.zh-Hans.md) 会在与序列中包含的日期对应的时间点更新其内容。

## 获取日期序列

- **entries(from:mode:)**：提供从给定日期附近开始的周期性日期序列。

## 符合以下协议：

- IteratorProtocol

- Sendable

- SendableMetatype

- Sequence


---
source: https://developer.apple.com/documentation/SwiftUI/PeriodicTimelineSchedule/Entries
crawled: 2025-12-04T13:16:06Z
---

# PeriodicTimelineSchedule.Entries

**Structure**

The sequence of dates in periodic schedule.

## Declaration

```swift
struct Entries
```

## Overview

The [entries(from:mode:)](entries_from_mode.zh-Hans.md) method returns a value of this type, which is a [doc://com.apple.documentation/documentation/Swift/Sequence] of periodic dates in ascending order. A [TimelineView](../TimelineView.zh-Hans.md) that you create updates its content at the moments in time corresponding to the dates included in the sequence.

## Getting the sequence of dates

- **entries(from:mode:)**: Provides a sequence of periodic dates starting from around a given date.

## Conforms To

- IteratorProtocol
- Sendable
- SendableMetatype
- Sequence

