---
来源： https://developer.apple.com/documentation/SwiftUI/TimelineView/Context/cadence-swift.property
抓取时间： 2025-12-04T09:10:07Z
---

#节奏

**实例属性**

时间轴更新视图的速度。

## 声明

```swift
let cadence: TimelineView<Schedule, Content>.Context.Cadence
```

## 讨论

使用此值可隐藏更新速度快于视图当前更新速度的信息。例如，当节奏慢于 [live](Cadence-swift_enum/live.zh-Hans.md)时，可以隐藏数字计时器的毫秒分量。

由于[Cadence-swift.enum](Cadence-swift_enum.zh-Hans.md)枚举符合[doc://com.apple.documentation/documentation/Swift/Comparable]协议，因此可以使用关系运算符来比较步频。速度较慢的音调值较高，因此可以通过以下比较执行上述检查：

```swift
let hideMilliseconds = cadence > .live
```

## 获取节奏

- **TimelineView.Context.Cadence**：时间线视图接收更新的速率。


---
source: https://developer.apple.com/documentation/SwiftUI/TimelineView/Context/cadence-swift.property
crawled: 2025-12-04T09:10:07Z
---

# cadence

**Instance Property**

The rate at which the timeline updates the view.

## Declaration

```swift
let cadence: TimelineView<Schedule, Content>.Context.Cadence
```

## Discussion

Use this value to hide information that updates faster than the view’s current update rate. For example, you could hide the millisecond component of a digital timer when the cadence is anything slower than [live](Cadence-swift_enum/live.zh-Hans.md).

Because the [Cadence-swift.enum](Cadence-swift_enum.zh-Hans.md) enumeration conforms to the [doc://com.apple.documentation/documentation/Swift/Comparable] protocol, you can compare cadences with relational operators. Slower cadences have higher values, so you could perform the check described above with the following comparison:

```swift
let hideMilliseconds = cadence > .live
```

## Getting the cadence

- **TimelineView.Context.Cadence**: A rate at which timeline views can receive updates.

