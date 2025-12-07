---
来源： https://developer.apple.com/documentation/SwiftUI/TimelineSchedule/Entries
抓取时间： 2025-12-03T06:15:36Z
---

# 条目

**相关类型**

计划表中的日期顺序。

## 声明

```swift
associatedtype Entries : Sequence where Self.Entries.Element == Date
```

## 讨论

[entries(from:mode:)](entries_from_mode.zh-Hans.md)方法返回该类型的值，即按升序排列的日期的[doc://com.apple.documentation/documentation/Swift/Sequence]。使用计划表创建的[TimelineView](../TimelineView.zh-Hans.md) 在与序列中包含的日期相对应的时刻更新其内容。

## 获取日期序列

- **entries(from:mode:)**：提供一个从给定日期开始的日期序列。


---
source: https://developer.apple.com/documentation/SwiftUI/TimelineSchedule/Entries
crawled: 2025-12-03T06:15:36Z
---

# Entries

**Associated Type**

The sequence of dates within a schedule.

## Declaration

```swift
associatedtype Entries : Sequence where Self.Entries.Element == Date
```

## Discussion

The [entries(from:mode:)](entries_from_mode.zh-Hans.md) method returns a value of this type, which is a [doc://com.apple.documentation/documentation/Swift/Sequence] of dates in ascending order. A [TimelineView](../TimelineView.zh-Hans.md) that you create with a schedule updates its content at the moments in time corresponding to the dates included in the sequence.

## Getting a sequence of dates

- **entries(from:mode:)**: Provides a sequence of dates starting around a given date.

