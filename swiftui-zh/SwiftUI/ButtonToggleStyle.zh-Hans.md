---
来源： https://developer.apple.com/documentation/SwiftUI/ButtonToggleStyle
抓取时间： 2025-12-03T06:09:52Z
---

# ButtonToggleStyle

**Structure**

切换样式，以按钮形式显示，其标签为标题。

### 声明

```swift
struct ButtonToggleStyle
```

## 概览

您也可以使用 [button](ToggleStyle/button.zh-Hans.md) 构建这种样式。

```swift
Toggle(isOn: $isFlagged) {
    Label("Flag", systemImage: "flag.fill")
}
.toggleStyle(.button)
```

## 创建切换样式

- **init()**：创建按钮切换样式。

## 支持类型

- **makeBody(configuration:)**：创建表示切换按钮主体的视图。

## 支持类型

- **DefaultToggleStyle**：默认的切换样式。
- **CheckboxToggleStyle**：显示复选框及其标签的切换样式。
- **SwitchToggleStyle**：显示前标签和后开关的切换样式。

## 符合

- 切换样式


---
source: https://developer.apple.com/documentation/SwiftUI/ButtonToggleStyle
crawled: 2025-12-03T06:09:52Z
---

# ButtonToggleStyle

**Structure**

A toggle style that displays as a button with its label as the title.

## Declaration

```swift
struct ButtonToggleStyle
```

## Overview

You can also use [button](ToggleStyle/button.zh-Hans.md) to construct this style.

```swift
Toggle(isOn: $isFlagged) {
    Label("Flag", systemImage: "flag.fill")
}
.toggleStyle(.button)
```

## Creating the toggle style

- **init()**: Creates a button toggle style.

## Supporting types

- **makeBody(configuration:)**: Creates a view that represents the body of a toggle button.

## Supporting types

- **DefaultToggleStyle**: The default toggle style.
- **CheckboxToggleStyle**: A toggle style that displays a checkbox followed by its label.
- **SwitchToggleStyle**: A toggle style that displays a leading label and a trailing switch.

## Conforms To

- ToggleStyle

