---
来源： https://developer.apple.com/documentation/SwiftUI/DatePickerStyle/field
抓取时间： 2025-12-03T06:09:29Z
---

# 字段

**类型属性**

日期选择器样式，用于在可编辑字段中显示组件。

## 声明

```swift
@MainActor @preconcurrency static var field: FieldDatePickerStyle { get }
```

## 讨论

当空间有限且用户希望选择特定日期和时间时，可以使用这种样式。不过，除非您的应用程序需要隐藏步进器，否则一般应使用 [stepperField](stepperField.zh-Hans.md) 代替这种样式。

## 获取内置日期选择器样式

- **automatic**：日期选择器的默认样式。
- **compact**：以紧凑的文本格式显示组件的日期选择器样式。
- **graphical**：显示交互式日历或时钟的日期选择器样式。
- **stepperField**：一种系统样式，在可编辑字段中显示组件，并带有可递增/递减所选组件的相邻步进器。
- **wheel**：一种日期选择器样式，在可滚动的滚轮中以列的形式显示每个组件。


---
source: https://developer.apple.com/documentation/SwiftUI/DatePickerStyle/field
crawled: 2025-12-03T06:09:29Z
---

# field

**Type Property**

A date picker style that displays the components in an editable field.

## Declaration

```swift
@MainActor @preconcurrency static var field: FieldDatePickerStyle { get }
```

## Discussion

You can use this style when space is constrained and users expect to make specific date and time selections. However, you should generally use [stepperField](stepperField.zh-Hans.md) instead of this style, unless your your app requires hiding the stepper.

## Getting built-in date picker styles

- **automatic**: The default style for date pickers.
- **compact**: A date picker style that displays the components in a compact, textual format.
- **graphical**: A date picker style that displays an interactive calendar or clock.
- **stepperField**: A system style that displays the components in an editable field, with adjoining stepper that can increment/decrement the selected component.
- **wheel**: A date picker style that displays each component as columns in a scrollable wheel.

