--- 来源：https://developer.apple.com/documentation/SwiftUI/TimelineView

抓取时间：2025-12-02T17:04:41Z

---

# TimelineView

**Structure**

一个根据您提供的计划更新的视图。

## 声明

```swift
struct TimelineView<Schedule, Content> where Schedule : TimelineSchedule
```

## 概述

时间线视图作为一个容器，本身没有外观。它会在预定的时间点重新绘制其包含的内容。例如，您可以每秒更新一次模拟计时器的表盘：

```swift
TimelineView(.periodic(from: startDate, by: 1)) { context in
    AnalogTimerView(date: context.date)
}
```

创建内容的闭包接收一个 [Context](TimelineView/Context.zh-Hans.md) 类型的输入，您可以使用该输入自定义内容的外观。上下文包含触发更新的 [date](TimelineView/Context/date.zh-Hans.md)。在上面的示例中，时间线视图会将该日期发送到您创建的模拟计时器，以便计时器视图知道如何在其表盘上绘制指针。

上下文还包含一个 [cadence-swift.property](TimelineView/Context/cadence-swift_property.zh-Hans.md) 属性，您可以使用它来隐藏不必要的细节。例如，您可以使用节奏来决定何时显示计时器的秒针：

```swift
TimelineView(.periodic(from: startDate, by: 1.0)) { context in
    AnalogTimerView(
        date: context.date,
        showSeconds: context.cadence <= .seconds)
}
```

系统可能会使用比计划更新频率更慢的节奏。例如，watchOS 上的视图在用户放下手腕时可能仍然可见，但更新频率较低，因此需要的细节也较少。

您可以通过创建符合 [TimelineSchedule](TimelineSchedule.zh-Hans.md) 协议的类型来定义自定义计划，或者使用内置的计划类型之一：

- 使用 [everyMinute](TimelineSchedule/everyMinute.zh-Hans.md) 计划在每分钟开始时更新。

- 使用 [periodic(from:by:)](TimelineSchedule/periodic_from_by.zh-Hans.md) 计划，可按自定义的开始时间和更新间隔定期更新。

- 当您需要有限次数或不规则的更新时，请使用 [explicit(_:)](TimelineSchedule/explicit.zh-Hans.md) 计划。

对于仅包含过去日期的计划，时间线视图将显示计划中的最后一个日期。对于仅包含未来日期的计划，时间线将使用当前日期绘制内容，直到第一个计划日期到来。

## 创建时间线

- **init(_:content:)**：创建一个使用给定计划的新时间线视图。

- **TimelineView.Context**：传递给时间线视图内容回调的信息。

## 已弃用的符号

- **init(_:content:)**：创建一个使用给定计划的新时间线视图。

## 初始化器

- **init(_:content:)**：创建一个使用给定日程安排的新时间线视图。

## 按日程更新视图

- **使用时间线更新 watchOS 应用**：即使用户界面处于非活动状态，也能无缝安排更新。

- **TimelineSchedule**：提供一系列日期作为日程安排的类型。

- **TimelineViewDefaultContext**：传递给时间线视图内容回调的信息。

## 符合以下标准

- Copyable

- View


---
source: https://developer.apple.com/documentation/SwiftUI/TimelineView
crawled: 2025-12-02T17:04:41Z
---

# TimelineView

**Structure**

A view that updates according to a schedule that you provide.

## Declaration

```swift
struct TimelineView<Schedule, Content> where Schedule : TimelineSchedule
```

## Overview

A timeline view acts as a container with no appearance of its own. Instead, it redraws the content it contains at scheduled points in time. For example, you can update the face of an analog timer once per second:

```swift
TimelineView(.periodic(from: startDate, by: 1)) { context in
    AnalogTimerView(date: context.date)
}
```

The closure that creates the content receives an input of type [Context](TimelineView/Context.zh-Hans.md) that you can use to customize the content’s appearance. The context includes the [date](TimelineView/Context/date.zh-Hans.md) that triggered the update. In the example above, the timeline view sends that date to an analog timer that you create so the timer view knows how to draw the hands on its face.

The context also includes a [cadence-swift.property](TimelineView/Context/cadence-swift_property.zh-Hans.md) property that you can use to hide unnecessary detail. For example, you can use the cadence to decide when it’s appropriate to display the timer’s second hand:

```swift
TimelineView(.periodic(from: startDate, by: 1.0)) { context in
    AnalogTimerView(
        date: context.date,
        showSeconds: context.cadence <= .seconds)
}
```

The system might use a cadence that’s slower than the schedule’s update rate. For example, a view on watchOS might remain visible when the user lowers their wrist, but update less frequently, and thus require less detail.

You can define a custom schedule by creating a type that conforms to the [TimelineSchedule](TimelineSchedule.zh-Hans.md) protocol, or use one of the built-in schedule types:

- Use an [everyMinute](TimelineSchedule/everyMinute.zh-Hans.md) schedule to update at the beginning of each minute.
- Use a [periodic(from:by:)](TimelineSchedule/periodic_from_by.zh-Hans.md) schedule to update periodically with a custom start time and interval between updates.
- Use an [explicit(_:)](TimelineSchedule/explicit.zh-Hans.md) schedule when you need a finite number, or irregular set of updates.

For a schedule containing only dates in the past, the timeline view shows the last date in the schedule. For a schedule containing only dates in the future, the timeline draws its content using the current date until the first scheduled date arrives.

## Creating a timeline

- **init(_:content:)**: Creates a new timeline view that uses the given schedule.
- **TimelineView.Context**: Information passed to a timeline view’s content callback.

## Deprecated symbols

- **init(_:content:)**: Creates a new timeline view that uses the given schedule.

## Initializers

- **init(_:content:)**: Creates a new timeline view that uses the given schedule.

## Updating a view on a schedule

- **Updating watchOS apps with timelines**: Seamlessly schedule updates to your user interface, even while it’s inactive.
- **TimelineSchedule**: A type that provides a sequence of dates for use as a schedule.
- **TimelineViewDefaultContext**: Information passed to a timeline view’s content callback.

## Conforms To

- Copyable
- View

