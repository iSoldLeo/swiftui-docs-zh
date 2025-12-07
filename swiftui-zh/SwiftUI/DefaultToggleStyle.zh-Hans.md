--- 来源：https://developer.apple.com/documentation/SwiftUI/DefaultToggleStyle
抓取时间：2025-12-03T06:09:51Z

---

# DefaultToggleStyle

**Structure**

默认切换样式。

## 声明

```swift
struct DefaultToggleStyle
```

## 概述

使用 [automatic](ToggleStyle/automatic.zh-Hans.md) 静态变量创建此样式：

```swift
Toggle("Enhance Sound", isOn: $isEnhanced)
    .toggleStyle(.automatic)
```

## 创建切换样式

- **init()**：创建默认切换样式。

## 支持的类型

- **makeBody(configuration:)**：创建表示切换主体的视图。

## 支持的类型

- **ButtonToggleStyle**：一种切换样式，显示为按钮，其标签作为标题。

- **CheckboxToggleStyle**：一种切换样式，显示为复选框，其后跟标签。

- **SwitchToggleStyle**：一种切换样式，显示前导标签和尾随开关。

## 符合以下规范

- ToggleStyle


---
source: https://developer.apple.com/documentation/SwiftUI/DefaultToggleStyle
crawled: 2025-12-03T06:09:51Z
---

# DefaultToggleStyle

**Structure**

The default toggle style.

## Declaration

```swift
struct DefaultToggleStyle
```

## Overview

Use the [automatic](ToggleStyle/automatic.zh-Hans.md) static variable to create this style:

```swift
Toggle("Enhance Sound", isOn: $isEnhanced)
    .toggleStyle(.automatic)
```

## Creating the toggle style

- **init()**: Creates a default toggle style.

## Supporting types

- **makeBody(configuration:)**: Creates a view that represents the body of a toggle.

## Supporting types

- **ButtonToggleStyle**: A toggle style that displays as a button with its label as the title.
- **CheckboxToggleStyle**: A toggle style that displays a checkbox followed by its label.
- **SwitchToggleStyle**: A toggle style that displays a leading label and a trailing switch.

## Conforms To

- ToggleStyle

