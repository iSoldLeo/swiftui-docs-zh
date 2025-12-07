---
来源： https://developer.apple.com/documentation/SwiftUI/AutomaticFormStyle
抓取时间： 2025-12-03T06:11:40Z
---

# AutomaticFormStyle

**Structure**

默认表单样式。

## 声明

```swift
struct AutomaticFormStyle
```

## 概览

使用 [automatic](FormStyle/automatic.zh-Hans.md) 静态变量创建此样式：

```swift
Form {
   ...
}
.formStyle(.automatic)
```

## 创建表格样式

- **init()**：创建默认表单样式。

## 支持类型

- **ColumnsFormStyle**：一种非滚动表单样式，标签列尾部对齐，数值列前部对齐。
- **GroupedFormStyle**：具有分组行的表格样式。

## 符合

- 表格样式


---
source: https://developer.apple.com/documentation/SwiftUI/AutomaticFormStyle
crawled: 2025-12-03T06:11:40Z
---

# AutomaticFormStyle

**Structure**

The default form style.

## Declaration

```swift
struct AutomaticFormStyle
```

## Overview

Use the [automatic](FormStyle/automatic.zh-Hans.md) static variable to create this style:

```swift
Form {
   ...
}
.formStyle(.automatic)
```

## Creating the form style

- **init()**: Creates a default form style.

## Supporting types

- **ColumnsFormStyle**: A non-scrolling form style with a trailing aligned column of labels next to a leading aligned column of values.
- **GroupedFormStyle**: A form style with grouped rows.

## Conforms To

- FormStyle

