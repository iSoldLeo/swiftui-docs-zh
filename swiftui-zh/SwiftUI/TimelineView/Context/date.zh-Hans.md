---
来源： https://developer.apple.com/documentation/SwiftUI/TimelineView/Context/date
抓取时间： 2025-12-04T09:10:06Z
---

# 日期

**实例属性**

触发当前视图更新的日程表中的日期。

## 声明

```swift
let date: Date
```

## 讨论

[TimelineView](../../TimelineView.zh-Hans.md)关闭第一次收到此日期时，可能已经是过去时了。例如，如果在 `10:09:55` 创建[everyMinute](../../TimelineSchedule/everyMinute.zh-Hans.md) 计划表，该计划表就会创建`10:09:00`、`10:10:00`、`10:11:00` 等条目。对此，时间轴视图会立即在`10:09:55`处执行初始更新，但上下文包含`10:09:00`日期条目。其后的条目在相应的时间到达。


---
source: https://developer.apple.com/documentation/SwiftUI/TimelineView/Context/date
crawled: 2025-12-04T09:10:06Z
---

# date

**Instance Property**

The date from the schedule that triggered the current view update.

## Declaration

```swift
let date: Date
```

## Discussion

The first time a [TimelineView](../../TimelineView.zh-Hans.md) closure receives this date, it might be in the past. For example, if you create an [everyMinute](../../TimelineSchedule/everyMinute.zh-Hans.md) schedule at `10:09:55`, the schedule creates entries `10:09:00`, `10:10:00`, `10:11:00`, and so on. In response, the timeline view performs an initial update immediately, at `10:09:55`, but the context contains the `10:09:00` date entry. Subsequent entries arrive at their corresponding times.

