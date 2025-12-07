---
来源： https://developer.apple.com/documentation/SwiftUI/WheelDatePickerStyle
抓取时间： 2025-12-03T06:09:38Z
---

# WheelDatePickerStyle

**Structure**

一种日期选择器样式，在可滚动的滚轮中以列的形式显示每个组件。

### 声明

```swift
@MainActor @preconcurrency struct WheelDatePickerStyle
```

## 概览

您也可以使用 [wheel](DatePickerStyle/wheel.zh-Hans.md) 构建这种样式。

## 创建日期选择器样式

- **init()**：创建轮式日期选择器样式的实例。

## 支持类型

- **DefaultDatePickerStyle**：日期选择器的默认样式。
- **CompactDatePickerStyle**：以紧凑的文本格式显示组件的日期选择器样式。
- **FieldDatePickerStyle**：以可编辑字段显示组件的日期选择器样式。
- **GraphicalDatePickerStyle**：显示交互式日历或时钟的日期选择器样式。
- **StepperFieldDatePickerStyle**：一种系统样式，可在可编辑字段中显示组件，并带有可递增/递减所选组件的相邻步进器。

## 符合

- 日期选择器样式


---
source: https://developer.apple.com/documentation/SwiftUI/WheelDatePickerStyle
crawled: 2025-12-03T06:09:38Z
---

# WheelDatePickerStyle

**Structure**

A date picker style that displays each component as columns in a scrollable wheel.

## Declaration

```swift
@MainActor @preconcurrency struct WheelDatePickerStyle
```

## Overview

You can also use [wheel](DatePickerStyle/wheel.zh-Hans.md) to construct this style.

## Creating the date picker style

- **init()**: Creates an instance of the wheel date picker style.

## Supporting types

- **DefaultDatePickerStyle**: The default style for date pickers.
- **CompactDatePickerStyle**: A date picker style that displays the components in a compact, textual format.
- **FieldDatePickerStyle**: A date picker style that displays the components in an editable field.
- **GraphicalDatePickerStyle**: A date picker style that displays an interactive calendar or clock.
- **StepperFieldDatePickerStyle**: A system style that displays the components in an editable field, with adjoining stepper that can increment/decrement the selected component.

## Conforms To

- DatePickerStyle

