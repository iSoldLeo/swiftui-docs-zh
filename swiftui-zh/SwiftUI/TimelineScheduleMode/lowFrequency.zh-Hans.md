--- 来源：https://developer.apple.com/documentation/SwiftUI/TimelineScheduleMode/lowFrequency
抓取时间：2025-12-04T13:15:59Z

---

# TimelineScheduleMode.lowFrequency

**Case**

一种降低日程更新频率的模式。

## 声明

```swift
case lowFrequency
```

## 讨论

在此模式下，日程应尽可能只生成“主要”更新。例如，为计时器提供更新的时间线在此模式下可能会将更新频率限制为每分钟一次。

## 获取时间线日程模式

- **TimelineScheduleMode.normal**：一种以日程的自然频率生成日程更新的模式。


---
source: https://developer.apple.com/documentation/SwiftUI/TimelineScheduleMode/lowFrequency
crawled: 2025-12-04T13:15:59Z
---

# TimelineScheduleMode.lowFrequency

**Case**

A mode that produces schedule updates at a reduced rate.

## Declaration

```swift
case lowFrequency
```

## Discussion

In this mode, the schedule should generate only “major” updates, if possible. For example, a timeline providing updates to a timer might restrict updates to once a minute while in this mode.

## Getting timeline schedule modes

- **TimelineScheduleMode.normal**: A mode that produces schedule updates at the schedule’s natural cadence.

