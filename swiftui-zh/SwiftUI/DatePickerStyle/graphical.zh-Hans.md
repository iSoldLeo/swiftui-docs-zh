---
来源： https://developer.apple.com/documentation/SwiftUI/DatePickerStyle/graphical
抓取时间： 2025-12-03T06:09:29Z
---

# 图形

**类型属性**

显示交互式日历或时钟的日期选择器样式。

## 声明

```swift
@MainActor @preconcurrency static var graphical: GraphicalDatePickerStyle { get }
```

## 讨论

当您想浏览日历中的天数，或想拥有时钟表面的外观时，这种样式非常有用。

## 获取内置日期选择器样式

- **automatic**：日期选择器的默认样式。
- **compact**：以紧凑的文本格式显示组件的日期选择器样式。
- **field**：以可编辑字段显示组件的日期选择器样式。
- **stepperField**：系统样式，在可编辑字段中显示组件，并带有可递增/递减所选组件的邻接步进器。
- **wheel**：一种日期选择器样式，在可滚动的滚轮中以列的形式显示每个组件。


---
source: https://developer.apple.com/documentation/SwiftUI/DatePickerStyle/graphical
crawled: 2025-12-03T06:09:29Z
---

# graphical

**Type Property**

A date picker style that displays an interactive calendar or clock.

## Declaration

```swift
@MainActor @preconcurrency static var graphical: GraphicalDatePickerStyle { get }
```

## Discussion

This style is useful when you want to allow browsing through days in a calendar, or when the look of a clock face is appropriate.

## Getting built-in date picker styles

- **automatic**: The default style for date pickers.
- **compact**: A date picker style that displays the components in a compact, textual format.
- **field**: A date picker style that displays the components in an editable field.
- **stepperField**: A system style that displays the components in an editable field, with adjoining stepper that can increment/decrement the selected component.
- **wheel**: A date picker style that displays each component as columns in a scrollable wheel.

