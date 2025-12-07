---
来源： https://developer.apple.com/documentation/SwiftUI/ExplicitTimelineSchedule/init(_:)
抓取时间： 2025-12-04T13:16:04Z
---

# init(_:)

**Initializer**

创建一个由明确日期序列组成的计划表。

## 声明

```swift
init(_ dates: Entries)
```

## 参数

- **dates**：时间轴视图更新的日期序列。使用单调递增的日期序列，并确保至少有一个日期在未来。

##讨论

使用[entries(from:mode:)](entries_from_mode.zh-Hans.md) 方法获取日期序列。


---
source: https://developer.apple.com/documentation/SwiftUI/ExplicitTimelineSchedule/init(_:)
crawled: 2025-12-04T13:16:04Z
---

# init(_:)

**Initializer**

Creates a schedule composed of an explicit sequence of dates.

## Declaration

```swift
init(_ dates: Entries)
```

## Parameters

- **dates**: The sequence of dates at which a timeline view updates. Use a monotonically increasing sequence of dates, and ensure that at least one is in the future.

## Discussion

Use the [entries(from:mode:)](entries_from_mode.zh-Hans.md) method to get the sequence of dates.

