---
来源：https://developer.apple.com/documentation/SwiftUI/AnimationTimelineSchedule/entries(from:mode:)
抓取时间：2025-12-04T13:16:01Z
---

# 条目（from:mode:)

**实例方法**

按动画时间表的频率返回条目。

## 声明

```swift
func entries(from start: Date, mode: TimelineScheduleMode) -> AnimationTimelineSchedule.Entries
```

## 讨论

在 `.lowFrequency` 模式下，不返回任何条目，从而有效地暂停动画。


---
source: https://developer.apple.com/documentation/SwiftUI/AnimationTimelineSchedule/entries(from:mode:)
crawled: 2025-12-04T13:16:01Z
---

# entries(from:mode:)

**Instance Method**

Returns entries at the frequency of the animation schedule.

## Declaration

```swift
func entries(from start: Date, mode: TimelineScheduleMode) -> AnimationTimelineSchedule.Entries
```

## Discussion

When in `.lowFrequency` mode, return no entries, effectively pausing the animation.

