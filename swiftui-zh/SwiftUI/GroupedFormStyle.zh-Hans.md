--- 来源：https://developer.apple.com/documentation/SwiftUI/GroupedFormStyle
抓取时间：2025-12-03T06:11:41Z

---

# GroupedFormStyle

**Structure**

一种带有分组行的表单样式。

## 声明

```swift
struct GroupedFormStyle
```

## 概述

此表单样式中的行具有前导对齐的标签和尾随对齐的控件，这些控件位于视觉上分组的区域内。

使用 [grouped](FormStyle/grouped.zh-Hans.md) 静态变量创建此样式：

```swift
Form {
   ...
}
.formStyle(.grouped)
```

## 创建表单样式

- **init()**：创建一个带有滚动分组行的表单样式。

## 支持的类型

- **AutomaticFormStyle**：默认表单样式。

- **ColumnsFormStyle**：一种非滚动表单样式，其特点是：在对齐的列值旁边，紧邻一列对齐的标签。

## 符合以下规范

- FormStyle


---
source: https://developer.apple.com/documentation/SwiftUI/GroupedFormStyle
crawled: 2025-12-03T06:11:41Z
---

# GroupedFormStyle

**Structure**

A form style with grouped rows.

## Declaration

```swift
struct GroupedFormStyle
```

## Overview

Rows in this form style have leading aligned labels and trailing aligned controls within visually grouped sections.

Use the [grouped](FormStyle/grouped.zh-Hans.md) static variable to create this style:

```swift
Form {
   ...
}
.formStyle(.grouped)
```

## Creating the form style

- **init()**: Creates a form style with scrolling, grouped rows.

## Supporting types

- **AutomaticFormStyle**: The default form style.
- **ColumnsFormStyle**: A non-scrolling form style with a trailing aligned column of labels next to a leading aligned column of values.

## Conforms To

- FormStyle

