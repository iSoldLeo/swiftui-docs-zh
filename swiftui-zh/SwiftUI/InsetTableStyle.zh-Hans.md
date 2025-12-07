---
来源： https://developer.apple.com/documentation/SwiftUI/InsetTableStyle
抓取时间： 2025-12-03T06:11:09Z
---

# InsetTableStyle

**Structure**

表格样式，用于描述从表格边缘嵌入内容和选区的表格的行为和外观。

### 声明

```swift
struct InsetTableStyle
```

## 概览

您也可以使用 [inset](TableStyle/inset.zh-Hans.md) 构建这种样式。

## 创建表格样式

- **init()**：创建默认的嵌入式表格样式，交替显示行背景。
- **init(alternatesRowBackgrounds:)**：创建具有可选交替行背景的嵌入式表格样式。

### 支持类型

- **AutomaticTableStyle**：当前上下文中的默认表格样式。
- **BorderedTableStyle**：描述带有标准边框的表格的行为和外观的表格样式。

## 符合

- 表格样式


---
source: https://developer.apple.com/documentation/SwiftUI/InsetTableStyle
crawled: 2025-12-03T06:11:09Z
---

# InsetTableStyle

**Structure**

The table style that describes the behavior and appearance of a table with its content and selection inset from the table edges.

## Declaration

```swift
struct InsetTableStyle
```

## Overview

You can also use [inset](TableStyle/inset.zh-Hans.md) to construct this style.

## Creating the table style

- **init()**: Creates a default inset table style, with alternating row backgrounds.
- **init(alternatesRowBackgrounds:)**: Creates an inset table style with optional alternating row backgrounds.

## Supporting types

- **AutomaticTableStyle**: The default table style in the current context.
- **BorderedTableStyle**: The table style that describes the behavior and appearance of a table with standard border.

## Conforms To

- TableStyle

