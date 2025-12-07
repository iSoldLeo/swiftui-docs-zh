---
来源： https://developer.apple.com/documentation/SwiftUI/TimelineView/Context
抓取时间： 2025-12-03T04:53:34Z
---

# TimelineView.Context

**Structure**

传递给时间轴视图内容回调的信息。

## 声明

```swift
struct Context
```

## 概览

上下文既包括触发回调的日程表中的[date](Context/date.zh-Hans.md)，也包括可用于自定义视图外观的[cadence-swift.property](Context/cadence-swift_property.zh-Hans.md)。例如，您可以选择只在[seconds](Context/Cadence-swift_enum/seconds.zh-Hans.md) 或更快时显示模拟时钟的秒针。

## 获取日期

- **date**：触发当前视图更新的计划表中的日期。

## 获取周期

- **cadence**：时间轴更新视图的速率。
- **TimelineView.Context.Cadence**：时间线视图可以接收更新的速率。

## 使上下文无效

- **invalidateTimelineContent()**：重置系统在时间轴上的任何预渲染视图。

## 创建时间轴

- **init(_:content:)**：创建使用给定时间表的新时间线视图。


---
source: https://developer.apple.com/documentation/SwiftUI/TimelineView/Context
crawled: 2025-12-03T04:53:34Z
---

# TimelineView.Context

**Structure**

Information passed to a timeline view’s content callback.

## Declaration

```swift
struct Context
```

## Overview

The context includes both the [date](Context/date.zh-Hans.md) from the schedule that triggered the callback, and a [cadence-swift.property](Context/cadence-swift_property.zh-Hans.md) that you can use to customize the appearance of your view. For example, you might choose to display the second hand of an analog clock only when the cadence is [seconds](Context/Cadence-swift_enum/seconds.zh-Hans.md) or faster.

## Getting the date

- **date**: The date from the schedule that triggered the current view update.

## Getting the cadence

- **cadence**: The rate at which the timeline updates the view.
- **TimelineView.Context.Cadence**: A rate at which timeline views can receive updates.

## Invalidating the context

- **invalidateTimelineContent()**: Resets any pre-rendered views the system has from the timeline.

## Creating a timeline

- **init(_:content:)**: Creates a new timeline view that uses the given schedule.

