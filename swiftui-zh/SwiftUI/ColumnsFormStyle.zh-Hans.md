---
来源： https://developer.apple.com/documentation/SwiftUI/ColumnsFormStyle
抓取时间： 2025-12-03T06:11:41Z
---

# ColumnsFormStyle

**Structure**

一种非滚动表单样式，尾部对齐的标签列紧邻前部对齐的数值列。

### 声明

```swift
struct ColumnsFormStyle
```

## 概览

使用 [columns](FormStyle/columns.zh-Hans.md) 静态变量创建此样式：

```swift
Form {
   ...
}
.formStyle(.columns)
```

## 创建表格样式

- **init()**：一种非滚动表单样式，其标签列尾部对齐，值列前部对齐。

## 支持类型

- **AutomaticFormStyle**：默认表格样式。
- **GroupedFormStyle**：具有分组行的表单样式。

## 符合

- 表格样式


---
source: https://developer.apple.com/documentation/SwiftUI/ColumnsFormStyle
crawled: 2025-12-03T06:11:41Z
---

# ColumnsFormStyle

**Structure**

A non-scrolling form style with a trailing aligned column of labels next to a leading aligned column of values.

## Declaration

```swift
struct ColumnsFormStyle
```

## Overview

Use the [columns](FormStyle/columns.zh-Hans.md) static variable to create this style:

```swift
Form {
   ...
}
.formStyle(.columns)
```

## Creating the form style

- **init()**: A non-scrolling form style with a trailing aligned column of labels next to a leading aligned column of values.

## Supporting types

- **AutomaticFormStyle**: The default form style.
- **GroupedFormStyle**: A form style with grouped rows.

## Conforms To

- FormStyle

