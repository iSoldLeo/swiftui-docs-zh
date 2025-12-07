---
来源： https://developer.apple.com/documentation/SwiftUI/DatePickerStyle
抓取时间： 2025-12-02T17:33:06Z
---

# DatePickerStyle

**Protocol**

一种指定视图层次结构中所有日期选择器的外观和交互方式的类型。

### 声明

```swift
@MainActor @preconcurrency protocol DatePickerStyle
```

## 概览

要为视图层次结构配置当前日期选择器样式，请使用 [datePickerStyle(_:)](View/datePickerStyle.zh-Hans.md) 修改器。

如果符合该协议的类型的基本声明中包含了该协议，则该类型将继承`@preconcurrency @MainActor` 隔离协议：

```swift
struct MyCustomType: Transition {
    // `@preconcurrency @MainActor` isolation by default
}
```

默认情况下与主要角色隔离，但这不是必须的。在扩展声明中声明一致性，就可以不使用主要角色隔离：

```swift
extension MyCustomType: Transition {
    // `nonisolated` by default
}
```

## 获取内置日期选择器样式

- **automatic**：日期选择器的默认样式。
- **compact**：日期选择器样式，以紧凑的文本格式显示组件。
- **field**：以可编辑字段显示组件的日期选择器样式。
- **graphical**：显示交互式日历或时钟的日期选择器样式。
- **stepperField**：一种系统样式，可在可编辑字段中显示组件，并带有可递增/递减所选组件的相邻步进器。
- **wheel**：一种日期选择器样式，在可滚动的滚轮中以列的形式显示每个组件。

## 创建自定义日期选择器样式

- **makeBody(configuration:)**：返回`DatePicker`的外观和交互内容。
- **DatePickerStyleConfiguration**：`DatePicker`的属性。
- **DatePickerStyle.Configuration**：`DatePicker`属性的类型别名。
- **Body**：表示`DatePicker`外观和交互的视图。

## 支持类型

- **DefaultDatePickerStyle**：日期选择器的默认样式。
- **CompactDatePickerStyle**：日期选择器样式，以紧凑的文本格式显示组件。
- **FieldDatePickerStyle**：以可编辑字段显示组件的日期选择器样式。
- **GraphicalDatePickerStyle**：显示交互式日历或时钟的日期选择器样式。
- **StepperFieldDatePickerStyle**：一种系统样式，在可编辑字段中显示组件，并带有可递增/递减所选组件的相邻步进器。
- **WheelDatePickerStyle**：一种日期选择器样式，在可滚动的滚轮中以列的形式显示每个组件。

## 选取器样式

- **pickerStyle(_:)**：为该视图中的选取器设置样式。
- **PickerStyle**：指定视图层次结构中所有拾取器的外观和交互的类型。
- **datePickerStyle(_:)**：为该视图中的日期选取器设置样式。

## 符合类型

- CompactDatePickerStyle
- DefaultDatePickerStyle
- FieldDatePickerStyle
- GraphicalDatePickerStyle
- StepperFieldDatePickerStyle
- 轮式日期选择器样式


---
source: https://developer.apple.com/documentation/SwiftUI/DatePickerStyle
crawled: 2025-12-02T17:33:06Z
---

# DatePickerStyle

**Protocol**

A type that specifies the appearance and interaction of all date pickers within a view hierarchy.

## Declaration

```swift
@MainActor @preconcurrency protocol DatePickerStyle
```

## Overview

To configure the current date picker style for a view hierarchy, use the [datePickerStyle(_:)](View/datePickerStyle.zh-Hans.md) modifier.

A type conforming to this protocol inherits `@preconcurrency @MainActor` isolation from the protocol if the conformance is included in the type’s base declaration:

```swift
struct MyCustomType: Transition {
    // `@preconcurrency @MainActor` isolation by default
}
```

Isolation to the main actor is the default, but it’s not required. Declare the conformance in an extension to opt out of main actor isolation:

```swift
extension MyCustomType: Transition {
    // `nonisolated` by default
}
```

## Getting built-in date picker styles

- **automatic**: The default style for date pickers.
- **compact**: A date picker style that displays the components in a compact, textual format.
- **field**: A date picker style that displays the components in an editable field.
- **graphical**: A date picker style that displays an interactive calendar or clock.
- **stepperField**: A system style that displays the components in an editable field, with adjoining stepper that can increment/decrement the selected component.
- **wheel**: A date picker style that displays each component as columns in a scrollable wheel.

## Creating custom date picker styles

- **makeBody(configuration:)**: Returns the appearance and interaction content for a `DatePicker`.
- **DatePickerStyleConfiguration**: The properties of a `DatePicker`.
- **DatePickerStyle.Configuration**: A type alias for the properties of a `DatePicker`.
- **Body**: A view representing the appearance and interaction of a `DatePicker`.

## Supporting types

- **DefaultDatePickerStyle**: The default style for date pickers.
- **CompactDatePickerStyle**: A date picker style that displays the components in a compact, textual format.
- **FieldDatePickerStyle**: A date picker style that displays the components in an editable field.
- **GraphicalDatePickerStyle**: A date picker style that displays an interactive calendar or clock.
- **StepperFieldDatePickerStyle**: A system style that displays the components in an editable field, with adjoining stepper that can increment/decrement the selected component.
- **WheelDatePickerStyle**: A date picker style that displays each component as columns in a scrollable wheel.

## Styling pickers

- **pickerStyle(_:)**: Sets the style for pickers within this view.
- **PickerStyle**: A type that specifies the appearance and interaction of all pickers within a view hierarchy.
- **datePickerStyle(_:)**: Sets the style for date pickers within this view.

## Conforming Types

- CompactDatePickerStyle
- DefaultDatePickerStyle
- FieldDatePickerStyle
- GraphicalDatePickerStyle
- StepperFieldDatePickerStyle
- WheelDatePickerStyle

