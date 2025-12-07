---
来源： https://developer.apple.com/documentation/swiftui/datepicker
抓取时间： 2025-12-04T11:34:01Z
---

# 日期选择器

**Structure**

用于选择绝对日期的控件。

## 声明

```swift
struct DatePicker<Label> where Label : View
```

## 概览

使用`DatePicker` 时，您需要提供一个视图，允许用户选择日历日期和时间。该视图绑定到一个 [doc://com.apple.documentation/documentation/Foundation/Date] 实例。

下面的示例创建了一个基本的`DatePicker`，在 iOS 上显示为代表日期的文本。此示例只显示日历日期，而不显示时间。当用户点击或单击文本时，日历视图会以动画形式显示，用户可以从中选择一个日期。当用户取消日历视图时，视图会更新绑定的 [doc://com.apple.documentation/documentation/Foundation/Date]。

```swift
@State private var date = Date()

var body: some View {
    DatePicker(
        "Start Date",
        selection: $date,
        displayedComponents: [.date]
    )
}
```



如果需要在标签中添加副标题，可使用视图创建器创建多个`Text` 视图，其中第一个文本代表标题，第二个文本代表副标题：

```swift
@State private var date = Date()

var body: some View {
    DatePicker(selection: $date) {
        Text("Start Date")
        Text("Select the starting date for the event")
    }
}
```

您可以将`DatePicker` 限制在特定的日期范围内，只允许选择某个日期之前或之后的内容，或两个日期之间的内容。下面的示例显示了一个日期时间选择器，它只允许选择 2021 年内的日期（`UTC` 时区）。

```swift
@State private var date = Date()
let dateRange: ClosedRange<Date> = {
    let calendar = Calendar.current
    let startComponents = DateComponents(year: 2021, month: 1, day: 1)
    let endComponents = DateComponents(year: 2021, month: 12, day: 31, hour: 23, minute: 59, second: 59)
    return calendar.date(from:startComponents)!
        ...
        calendar.date(from:endComponents)!
}()

var body: some View {
    DatePicker(
        "Start Date",
         selection: $date,
         in: dateRange,
         displayedComponents: [.date, .hourAndMinute]
    )
}
```



### 日期选择器的样式

要使用不同风格的日期选择器，请使用[datePickerStyle(_:)](View/datePickerStyle.zh-Hans.md) 视图修改器。下面的示例显示了图形日期选择器样式。

```swift
@State private var date = Date()

var body: some View {
    DatePicker(
        "Start Date",
        selection: $date,
        displayedComponents: [.date]
    )
    .datePickerStyle(.graphical)
}
```



## 为任意日期创建日期选择器

- **init(_:selection:displayedComponents:)**：创建一个实例，用于选择范围不受限制的`Date`。
- **init(selection:displayedComponents:label:)**：创建一个选择范围未限定的`Date` 的实例。

## 为特定日期创建日期选择器

- **init(_:selection:in:displayedComponents:)**：创建一个在封闭范围内选择`Date` 的实例。
- **init(selection:in:displayedComponents:label:)**：创建一个在封闭范围内选择`Date` 的实例。

## 设置日期选择器组件

- **DatePicker.Components**
- **DatePickerComponents**

## 选择日期

- **datePickerStyle(_:)**：设置该视图中日期选择器的样式。
- **MultiDatePicker**：用于选择多个日期的控件。
- **calendar**：视图处理日期时应使用的当前日历。
- **timeZone**：视图处理日期时应使用的当前时区。

## 符合

- 视图


---
source: https://developer.apple.com/documentation/swiftui/datepicker
crawled: 2025-12-04T11:34:01Z
---

# DatePicker

**Structure**

A control for selecting an absolute date.

## Declaration

```swift
struct DatePicker<Label> where Label : View
```

## Overview

Use a `DatePicker` when you want to provide a view that allows the user to select a calendar date, and optionally a time. The view binds to a [doc://com.apple.documentation/documentation/Foundation/Date] instance.

The following example creates a basic `DatePicker`, which appears on iOS as text representing the date. This example limits the display to only the calendar date, not the time. When the user taps or clicks the text, a calendar view animates in, from which the user can select a date. When the user dismisses the calendar view, the view updates the bound [doc://com.apple.documentation/documentation/Foundation/Date].

```swift
@State private var date = Date()

var body: some View {
    DatePicker(
        "Start Date",
        selection: $date,
        displayedComponents: [.date]
    )
}
```



For cases where adding a subtitle to the label is desired, use a view builder that creates multiple `Text` views where the first text represents the title and the second text represents the subtitle:

```swift
@State private var date = Date()

var body: some View {
    DatePicker(selection: $date) {
        Text("Start Date")
        Text("Select the starting date for the event")
    }
}
```

You can limit the `DatePicker` to specific ranges of dates, allowing selections only before or after a certain date, or between two dates. The following example shows a date-and-time picker that only permits selections within the year 2021 (in the `UTC` time zone).

```swift
@State private var date = Date()
let dateRange: ClosedRange<Date> = {
    let calendar = Calendar.current
    let startComponents = DateComponents(year: 2021, month: 1, day: 1)
    let endComponents = DateComponents(year: 2021, month: 12, day: 31, hour: 23, minute: 59, second: 59)
    return calendar.date(from:startComponents)!
        ...
        calendar.date(from:endComponents)!
}()

var body: some View {
    DatePicker(
        "Start Date",
         selection: $date,
         in: dateRange,
         displayedComponents: [.date, .hourAndMinute]
    )
}
```



### Styling date pickers

To use a different style of date picker, use the [datePickerStyle(_:)](View/datePickerStyle.zh-Hans.md) view modifier. The following example shows the graphical date picker style.

```swift
@State private var date = Date()

var body: some View {
    DatePicker(
        "Start Date",
        selection: $date,
        displayedComponents: [.date]
    )
    .datePickerStyle(.graphical)
}
```



## Creating a date picker for any date

- **init(_:selection:displayedComponents:)**: Creates an instance that selects a `Date` with an unbounded range.
- **init(selection:displayedComponents:label:)**: Creates an instance that selects a `Date` with an unbounded range.

## Creating a date picker for specific dates

- **init(_:selection:in:displayedComponents:)**: Creates an instance that selects a `Date` in a closed range.
- **init(selection:in:displayedComponents:label:)**: Creates an instance that selects a `Date` in a closed range.

## Setting date picker components

- **DatePicker.Components**
- **DatePickerComponents**

## Choosing dates

- **datePickerStyle(_:)**: Sets the style for date pickers within this view.
- **MultiDatePicker**: A control for picking multiple dates.
- **calendar**: The current calendar that views should use when handling dates.
- **timeZone**: The current time zone that views should use when handling dates.

## Conforms To

- View

