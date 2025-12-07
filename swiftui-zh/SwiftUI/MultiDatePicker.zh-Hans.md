--- 来源：https://developer.apple.com/documentation/SwiftUI/MultiDatePicker
抓取时间：2025-12-02T17:27:32Z

---

# MultiDatePicker

**Structure**

用于选择多个日期的控件。

## 声明

```swift
struct MultiDatePicker<Label> where Label : View
```

## 概述

当您需要提供一个允许用户选择多个日期的视图时，请使用 `MultiDatePicker`。

以下示例创建了一个基本的 `MultiDatePicker`，它以日历视图的形式显示所选日期：

```swift
@State private var dates: Set<DateComponents> = []

var body: some View {
    MultiDatePicker("Dates Available", selection: $dates)
}
```

您可以将 `MultiDatePicker` 限制在特定的日期范围内，例如仅允许选择某个日期之前或之后的日期，或者选择两个日期之间的日期。以下示例展示了一个多日期选择器，它仅允许选择 2021 年 12 月 6 日和（不包括）16 日（`UTC` 时区）：

```swift
@Environment(\.calendar) var calendar
@Environment(\.timeZone) var timeZone

var bounds: Range<Date> {
    let start = calendar.date(from: DateComponents(
        timeZone: timeZone, year: 2022, month: 6, day: 6))!
    let end = calendar.date(from: DateComponents(
        timeZone: timeZone, year: 2022, month: 6, day: 16))!
    return start ..< end
}

@State private var dates: Set<DateComponents> = []

var body: some View {
    MultiDatePicker("Dates Available", selection: $dates, in: bounds)
}
```

您还可以通过环境变量指定其他语言环境、日历和时区。当您使用 [PreviewProvider](PreviewProvider.zh-Hans.md) 来查看多日期选择器在与您自身环境不同的环境中的运行情况时，此功能非常有用。

以下示例展示了一个具有自定义语言环境、日历和时区的多日期选择器：

```swift
struct ContentView_Previews: PreviewProvider {
    static var previews: some View {
        MultiDatePicker("Dates Available", selection: .constant([]))
            .environment(\.locale, Locale.init(identifier: "zh"))
            .environment(
                \.calendar, Calendar.init(identifier: .chinese))
            .environment(\.timeZone, TimeZone(abbreviation: "HKT")!)
    }
}
```

## 选择日期

- **init(_:selection:)**：创建一个实例，用于选择多个日期，且选择范围无限制。

- **init(selection:label:)**：创建一个实例，用于选择多个日期，且选择范围无限制。

## 选择日期范围

- **init(_:selection:in:)**：创建一个实例，用于选择某个起始日期及之后的多个日期。

- **init(selection:in:label:)**：创建一个实例，用于选择某个起始日期及之后的多个日期。

## 选择日期

- **DatePicker**：用于选择绝对日期的控件。

- **datePickerStyle(_:)**：设置此视图中日期选择器的样式。

- **calendar**：视图在处理日期时应使用的当前日历。

- **timeZone**：视图在处理日期时应使用的当前时区。

## 符合以下视图

- 视图


---
source: https://developer.apple.com/documentation/SwiftUI/MultiDatePicker
crawled: 2025-12-02T17:27:32Z
---

# MultiDatePicker

**Structure**

A control for picking multiple dates.

## Declaration

```swift
struct MultiDatePicker<Label> where Label : View
```

## Overview

Use a `MultiDatePicker` when you want to provide a view that allows the user to select multiple dates.

The following example creates a basic `MultiDatePicker`, which appears as a calendar view representing the selected dates:

```swift
@State private var dates: Set<DateComponents> = []

var body: some View {
    MultiDatePicker("Dates Available", selection: $dates)
}
```

You can limit the `MultiDatePicker` to specific ranges of dates allowing selections only before or after a certain date or between two dates. The following example shows a multi-date picker that only permits selections within the 6th and (excluding) the 16th of December 2021 (in the `UTC` time zone):

```swift
@Environment(\.calendar) var calendar
@Environment(\.timeZone) var timeZone

var bounds: Range<Date> {
    let start = calendar.date(from: DateComponents(
        timeZone: timeZone, year: 2022, month: 6, day: 6))!
    let end = calendar.date(from: DateComponents(
        timeZone: timeZone, year: 2022, month: 6, day: 16))!
    return start ..< end
}

@State private var dates: Set<DateComponents> = []

var body: some View {
    MultiDatePicker("Dates Available", selection: $dates, in: bounds)
}
```

You can also specify an alternative locale, calendar and time zone through environment values. This can be useful when using a [PreviewProvider](PreviewProvider.zh-Hans.md) to see how your multi-date picker behaves in environments that differ from your own.

The following example shows a multi-date picker with a custom locale, calendar and time zone:

```swift
struct ContentView_Previews: PreviewProvider {
    static var previews: some View {
        MultiDatePicker("Dates Available", selection: .constant([]))
            .environment(\.locale, Locale.init(identifier: "zh"))
            .environment(
                \.calendar, Calendar.init(identifier: .chinese))
            .environment(\.timeZone, TimeZone(abbreviation: "HKT")!)
    }
}
```

## Picking dates

- **init(_:selection:)**: Creates an instance that selects multiple dates with an unbounded range.
- **init(selection:label:)**: Creates an instance that selects multiple dates with an unbounded range.

## Picking dates in a range

- **init(_:selection:in:)**: Creates an instance that selects multiple dates on or after some start date.
- **init(selection:in:label:)**: Creates an instance that selects multiple dates on or after some start date.

## Choosing dates

- **DatePicker**: A control for selecting an absolute date.
- **datePickerStyle(_:)**: Sets the style for date pickers within this view.
- **calendar**: The current calendar that views should use when handling dates.
- **timeZone**: The current time zone that views should use when handling dates.

## Conforms To

- View

