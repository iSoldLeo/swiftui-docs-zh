---
来源： https://developer.apple.com/documentation/SwiftUI/PaletteSelectionEffect
抓取时间： 2025-12-02T17:36:07Z
---

# 调色板选择效果

**Structure**

应用于调色板项目的选择效果。

## 声明

```swift
struct PaletteSelectionEffect
```

## 概览

您可以使用[paletteSelectionEffect(_:)](View/paletteSelectionEffect.zh-Hans.md) 视图修改器配置调色板项目的选择效果。

## 获取调色板选择效果

- **automatic**：选中时应用系统默认效果。
- **custom**：选择时不应用任何系统效果。
- **symbolVariant(_:)**：选择时应用指定的符号变体。

## 从一组选项中选择

- **Picker**：从一组互斥值中进行选择的控件。
- **pickerStyle(_:)**：为该视图中的拾取器设置样式。
- **horizontalRadioGroupLayout()**：为该视图中的单选组样式选取器设置样式，使其与布局内的单选按钮水平定位。
- **defaultWheelPickerItemHeight(_:)**：设置默认滚轮样式选取器项目高度。
- **defaultWheelPickerItemHeight**：滚轮样式选取器（如日期选取器）中项目的默认高度。
- **paletteSelectionEffect(_:)**：指定应用于调色板项目的选择效果。

## 符合

- 等价
- 可发送
- 可发送元数据类型


---
source: https://developer.apple.com/documentation/SwiftUI/PaletteSelectionEffect
crawled: 2025-12-02T17:36:07Z
---

# PaletteSelectionEffect

**Structure**

The selection effect to apply to a palette item.

## Declaration

```swift
struct PaletteSelectionEffect
```

## Overview

You can configure the selection effect of a palette item by using the [paletteSelectionEffect(_:)](View/paletteSelectionEffect.zh-Hans.md) view modifier.

## Getting palette selection effects

- **automatic**: Applies the system’s default effect when selected.
- **custom**: Does not apply any system effect when selected.
- **symbolVariant(_:)**: Applies the specified symbol variant when selected.

## Choosing from a set of options

- **Picker**: A control for selecting from a set of mutually exclusive values.
- **pickerStyle(_:)**: Sets the style for pickers within this view.
- **horizontalRadioGroupLayout()**: Sets the style for radio group style pickers within this view to be horizontally positioned with the radio buttons inside the layout.
- **defaultWheelPickerItemHeight(_:)**: Sets the default wheel-style picker item height.
- **defaultWheelPickerItemHeight**: The default height of an item in a wheel-style picker, such as a date picker.
- **paletteSelectionEffect(_:)**: Specifies the selection effect to apply to a palette item.

## Conforms To

- Equatable
- Sendable
- SendableMetatype

