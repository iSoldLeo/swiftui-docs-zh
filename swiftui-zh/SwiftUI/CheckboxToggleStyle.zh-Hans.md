--- 来源：https://developer.apple.com/documentation/SwiftUI/CheckboxToggleStyle
抓取时间：2025-12-03T06:09:53Z

---

# CheckboxToggleStyle

**Structure**

一种切换样式，显示一个复选框及其标签。

## 声明

```swift
struct CheckboxToggleStyle
```

## 概述

使用 [checkbox](ToggleStyle/checkbox.zh-Hans.md) 静态变量创建此样式：

```swift
Toggle("Close windows when quitting an app", isOn: $doesClose)
    .toggleStyle(.checkbox)
```

## 创建切换样式

- **init()**：创建复选框切换样式。

## 支持的类型

- **makeBody(configuration:)**：创建表示切换复选框主体的视图。

## 支持的类型

- **DefaultToggleStyle**：默认的切换样式。

- **ButtonToggleStyle**：一种切换样式，显示为按钮，其标签作为标题。

- **SwitchToggleStyle**：一种切换样式，显示一个前置标签和一个尾部开关。

## 符合以下规范

- ToggleStyle


---
source: https://developer.apple.com/documentation/SwiftUI/CheckboxToggleStyle
crawled: 2025-12-03T06:09:53Z
---

# CheckboxToggleStyle

**Structure**

A toggle style that displays a checkbox followed by its label.

## Declaration

```swift
struct CheckboxToggleStyle
```

## Overview

Use the [checkbox](ToggleStyle/checkbox.zh-Hans.md) static variable to create this style:

```swift
Toggle("Close windows when quitting an app", isOn: $doesClose)
    .toggleStyle(.checkbox)
```

## Creating the toggle style

- **init()**: Creates a checkbox toggle style.

## Supporting types

- **makeBody(configuration:)**: Creates a view that represents the body of a toggle checkbox.

## Supporting types

- **DefaultToggleStyle**: The default toggle style.
- **ButtonToggleStyle**: A toggle style that displays as a button with its label as the title.
- **SwitchToggleStyle**: A toggle style that displays a leading label and a trailing switch.

## Conforms To

- ToggleStyle

