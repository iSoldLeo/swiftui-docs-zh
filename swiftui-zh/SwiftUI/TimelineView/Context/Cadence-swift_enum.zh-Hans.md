---
来源： https://developer.apple.com/documentation/SwiftUI/TimelineView/Context/Cadence-swift.enum
抓取时间： 2025-12-04T09:10:08Z
---

# TimelineView.Context.Cadence

**Enumeration**

时间线视图接收更新的速率。

## 声明

```swift
enum Cadence
```

## 概览

使用向[TimelineView](../../TimelineView.zh-Hans.md) 中内容呈现的节奏来隐藏更新速度快于视图当前更新速度的信息。例如，当节奏为 [seconds](Cadence-swift_enum/seconds.zh-Hans.md) 或 [minutes](Cadence-swift_enum/minutes.zh-Hans.md) 时，您可以隐藏数字计时器的毫秒分量。

由于该枚举符合[doc://com.apple.documentation/documentation/Swift/Comparable] 协议，因此可以用关系运算符比较节奏。速度较慢的音调值较高，因此可以通过以下比较执行上述检查：

```swift
let hideMilliseconds = cadence > .live
```

## 获取节奏

- **TimelineView.Context.Cadence.live**：持续更新视图。
- **TimelineView.Context.Cadence.seconds**：大约每秒更新一次视图。
- **TimelineView.Context.Cadence.minutes**：大约每分钟更新一次视图。

## 获取节奏

- **cadence**：时间线更新视图的速度。

## 符合

- 可比较
- 可复制
- 等价
- 可散列
- 可发送
- 可发送元类型


---
source: https://developer.apple.com/documentation/SwiftUI/TimelineView/Context/Cadence-swift.enum
crawled: 2025-12-04T09:10:08Z
---

# TimelineView.Context.Cadence

**Enumeration**

A rate at which timeline views can receive updates.

## Declaration

```swift
enum Cadence
```

## Overview

Use the cadence presented to content in a [TimelineView](../../TimelineView.zh-Hans.md) to hide information that updates faster than the view’s current update rate. For example, you could hide the millisecond component of a digital timer when the cadence is [seconds](Cadence-swift_enum/seconds.zh-Hans.md) or [minutes](Cadence-swift_enum/minutes.zh-Hans.md).

Because this enumeration conforms to the [doc://com.apple.documentation/documentation/Swift/Comparable] protocol, you can compare cadences with relational operators. Slower cadences have higher values, so you could perform the check described above with the following comparison:

```swift
let hideMilliseconds = cadence > .live
```

## Getting cadences

- **TimelineView.Context.Cadence.live**: Updates the view continuously.
- **TimelineView.Context.Cadence.seconds**: Updates the view approximately once per second.
- **TimelineView.Context.Cadence.minutes**: Updates the view approximately once per minute.

## Getting the cadence

- **cadence**: The rate at which the timeline updates the view.

## Conforms To

- Comparable
- Copyable
- Equatable
- Hashable
- Sendable
- SendableMetatype

