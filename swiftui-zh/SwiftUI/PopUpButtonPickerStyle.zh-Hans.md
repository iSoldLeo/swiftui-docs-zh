--- 来源：https://developer.apple.com/documentation/SwiftUI/PopUpButtonPickerStyle
抓取时间：2025-12-03T06:09:27Z

---

# PopUpButtonPickerStyle

**Structure**

当用户按下按钮时，此选择器样式会将选项以菜单形式呈现。

## 声明

```swift
struct PopUpButtonPickerStyle
```

## 概述

当选项超过五个时，请使用此样式。当选项少于五个时，请考虑使用 [RadioGroupPickerStyle](RadioGroupPickerStyle.zh-Hans.md)。

按钮本身指示当前选中的选项。您可以在选项集中添加其他控件，例如用于自定义选项列表的按钮。

要将此样式应用于选择器或包含选择器的视图，请使用 [pickerStyle(_:)](View/pickerStyle.zh-Hans.md) 修饰符。

### 创建选择器样式

- [init()](PopUpButtonPickerStyle/init.zh-Hans.md)

## 初始化器

- **init()**：创建弹出按钮选择器样式。

## 符合以下规范

- PickerStyle


---
source: https://developer.apple.com/documentation/SwiftUI/PopUpButtonPickerStyle
crawled: 2025-12-03T06:09:27Z
---

# PopUpButtonPickerStyle

**Structure**

A picker style that presents the options as a menu when the user presses a button.

## Declaration

```swift
struct PopUpButtonPickerStyle
```

## Overview

Use this style when there are more than five options. Consider using [RadioGroupPickerStyle](RadioGroupPickerStyle.zh-Hans.md) when there are fewer than five options.

The button itself indicates the selected option. You can include additional controls in the set of options, such as a button to customize the list of options.

To apply this style to a picker, or to a view that contains pickers, use the [pickerStyle(_:)](View/pickerStyle.zh-Hans.md) modifier.

### Creating the picker style

- [init()](PopUpButtonPickerStyle/init.zh-Hans.md)

## Initializers

- **init()**: Creates a pop-up button picker style.

## Conforms To

- PickerStyle

