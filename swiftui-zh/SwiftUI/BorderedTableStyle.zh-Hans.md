---
来源： https://developer.apple.com/documentation/SwiftUI/BorderedTableStyle
抓取时间： 2025-12-03T06:11:10Z
---

# BorderedTableStyle

**Structure**

描述带有标准边框的表格的行为和外观的表格样式。

### 声明

```swift
struct BorderedTableStyle
```

## 概览

您也可以使用 [bordered](TableStyle/bordered.zh-Hans.md) 构建这种样式。

## 创建表格样式

- **init()**：创建默认的带边框表格样式，交替显示行背景。
- **init(alternatesRowBackgrounds:)**：创建带有可选交替行背景的嵌入式表格样式。

### 支持类型

- **AutomaticTableStyle**：当前上下文中的默认表格样式。
- **InsetTableStyle**：描述表格行为和外观的表格样式，其内容和选择从表格边缘嵌入。

## 符合

- 表格样式


---
source: https://developer.apple.com/documentation/SwiftUI/BorderedTableStyle
crawled: 2025-12-03T06:11:10Z
---

# BorderedTableStyle

**Structure**

The table style that describes the behavior and appearance of a table with standard border.

## Declaration

```swift
struct BorderedTableStyle
```

## Overview

You can also use [bordered](TableStyle/bordered.zh-Hans.md) to construct this style.

## Creating the table style

- **init()**: Creates a default bordered table style, with alternating row backgrounds.
- **init(alternatesRowBackgrounds:)**: Creates an inset table style with optional alternating row backgrounds.

## Supporting types

- **AutomaticTableStyle**: The default table style in the current context.
- **InsetTableStyle**: The table style that describes the behavior and appearance of a table with its content and selection inset from the table edges.

## Conforms To

- TableStyle

