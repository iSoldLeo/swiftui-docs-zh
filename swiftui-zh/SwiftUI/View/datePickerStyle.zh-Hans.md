--- 来源：https://developer.apple.com/documentation/SwiftUI/View/datePickerStyle(_:)

抓取时间：2025-12-02T17:33:05Z

---

# datePickerStyle(_:)

**实例方法**

设置此视图中日期选择器的样式。

## 声明

```swift
nonisolated func datePickerStyle<S>(_ style: S) -> some View where S : DatePickerStyle

```

## 选择日期

- **DatePicker**：用于选择绝对日期的控件。

- **MultiDatePicker**：用于选择多个日期的控件。

- **calendar**：视图在处理日期时应使用的当前日历。

- **timeZone**：视图在处理日期时应使用的当前时区。


---
source: https://developer.apple.com/documentation/SwiftUI/View/datePickerStyle(_:)
crawled: 2025-12-02T17:33:05Z
---

# datePickerStyle(_:)

**Instance Method**

Sets the style for date pickers within this view.

## Declaration

```swift
nonisolated func datePickerStyle<S>(_ style: S) -> some View where S : DatePickerStyle

```

## Choosing dates

- **DatePicker**: A control for selecting an absolute date.
- **MultiDatePicker**: A control for picking multiple dates.
- **calendar**: The current calendar that views should use when handling dates.
- **timeZone**: The current time zone that views should use when handling dates.

