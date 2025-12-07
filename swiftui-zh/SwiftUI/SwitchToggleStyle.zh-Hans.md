---
来源： https://developer.apple.com/documentation/SwiftUI/SwitchToggleStyle
抓取时间： 2025-12-03T06:09:53Z
---

# SwitchToggleStyle

**Structure**

一种切换样式，显示前面的标签和后面的开关。

### 声明

```swift
struct SwitchToggleStyle
```

## 概览

使用 [switch](ToggleStyle/switch.zh-Hans.md) 静态变量创建此样式：

```swift
Toggle("Enhance Sound", isOn: $isEnhanced)
    .toggleStyle(.switch)
```

## 创建切换样式

- **init()**：创建开关切换样式。

## 支持类型

- **makeBody(configuration:)**：创建表示切换开关主体的视图。

## 过时的初始化程序

- **init(tint:)**：创建带有颜色的开关样式。

## 支持类型

- **DefaultToggleStyle**：默认的切换样式。
- **ButtonToggleStyle**：以按钮形式显示的切换样式，其标签为标题。
- **CheckboxToggleStyle**：一种切换样式，显示一个复选框，后面跟有标签。

## 符合

- 切换样式


---
source: https://developer.apple.com/documentation/SwiftUI/SwitchToggleStyle
crawled: 2025-12-03T06:09:53Z
---

# SwitchToggleStyle

**Structure**

A toggle style that displays a leading label and a trailing switch.

## Declaration

```swift
struct SwitchToggleStyle
```

## Overview

Use the [switch](ToggleStyle/switch.zh-Hans.md) static variable to create this style:

```swift
Toggle("Enhance Sound", isOn: $isEnhanced)
    .toggleStyle(.switch)
```

## Creating the toggle style

- **init()**: Creates a switch toggle style.

## Supporting types

- **makeBody(configuration:)**: Creates a view that represents the body of a toggle switch.

## Deprecated initializers

- **init(tint:)**: Creates a switch style with a tint color.

## Supporting types

- **DefaultToggleStyle**: The default toggle style.
- **ButtonToggleStyle**: A toggle style that displays as a button with its label as the title.
- **CheckboxToggleStyle**: A toggle style that displays a checkbox followed by its label.

## Conforms To

- ToggleStyle

