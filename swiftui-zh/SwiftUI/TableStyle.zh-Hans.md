---
来源： https://developer.apple.com/documentation/SwiftUI/TableStyle
抓取时间： 2025-12-02T17:33:23Z
---

# TableStyle

**Protocol**

将自定义外观应用于视图中所有表格的类型。

### 声明

```swift
@MainActor @preconcurrency protocol TableStyle
```

## 概览

要为视图层次结构配置当前表格样式，请使用 [tableStyle(_:)](View/tableStyle.zh-Hans.md) 修饰符。

如果符合该协议的类型的基本声明中包含了该协议，则该类型将继承该协议的 `@preconcurrency @MainActor`隔离：

```swift
struct MyCustomType: Transition {
    // `@preconcurrency @MainActor` isolation by default
}
```

默认情况下与主要角色隔离，但这不是必须的。在扩展声明中声明一致性，就可以不使用主要角色隔离：

```swift
extension MyCustomType: Transition {
    // `nonisolated` by default
}
```

## 获取内置表格样式

- **automatic**：当前上下文中的默认表格样式。
- **inset**：描述表格行为和外观的表格样式，其内容和选择从表格边缘嵌入。
- **bordered**：描述带有标准边框的表格的行为和外观的表格样式。

## 创建自定义表格样式

- **makeBody(configuration:)**：创建表示表格主体的视图。
- **TableStyle.Configuration**：表的属性。
- **Body**：视图：表示表主体的视图。

## 过时样式

- **inset(alternatesRowBackgrounds:)**：表格样式，用于描述表格的行为和外观，其内容和选择从表格边缘嵌入。
- **bordered(alternatesRowBackgrounds:)**：描述带有标准边框的表格的行为和外观的表格样式。

### 支持类型

- **AutomaticTableStyle**：当前上下文中的默认表格样式。
- **InsetTableStyle**：描述表格行为和外观的表格样式，其内容和选择从表格边缘嵌入。
- **BorderedTableStyle**：描述带有标准边框的表格的行为和外观的表格样式。

## 集合视图样式

- **listStyle(_:)**：为该视图中的列表设置样式。
- **ListStyle**：描述列表行为和外观的协议。
- **tableStyle(_:)**：设置该视图中表格的样式。
- **TableStyleConfiguration**：表格的属性。
- **disclosureGroupStyle(_:)**：设置该视图中披露组的样式。
- **DisclosureGroupStyle**：一种类型，用于指定视图层次结构中披露组的外观和交互。

## 符合类型

- 自动表格样式
- 有边框表格样式
- 嵌入式表格样式


---
source: https://developer.apple.com/documentation/SwiftUI/TableStyle
crawled: 2025-12-02T17:33:23Z
---

# TableStyle

**Protocol**

A type that applies a custom appearance to all tables within a view.

## Declaration

```swift
@MainActor @preconcurrency protocol TableStyle
```

## Overview

To configure the current table style for a view hierarchy, use the [tableStyle(_:)](View/tableStyle.zh-Hans.md) modifier.

A type conforming to this protocol inherits `@preconcurrency @MainActor` isolation from the protocol if the conformance is included in the type’s base declaration:

```swift
struct MyCustomType: Transition {
    // `@preconcurrency @MainActor` isolation by default
}
```

Isolation to the main actor is the default, but it’s not required. Declare the conformance in an extension to opt out of main actor isolation:

```swift
extension MyCustomType: Transition {
    // `nonisolated` by default
}
```

## Getting built-in table styles

- **automatic**: The default table style in the current context.
- **inset**: The table style that describes the behavior and appearance of a table with its content and selection inset from the table edges.
- **bordered**: The table style that describes the behavior and appearance of a table with standard border.

## Creating custom table styles

- **makeBody(configuration:)**: Creates a view that represents the body of a table.
- **TableStyle.Configuration**: The properties of a table.
- **Body**: A view that represents the body of a table.

## Deprecated styles

- **inset(alternatesRowBackgrounds:)**: The table style that describes the behavior and appearance of a table with its content and selection inset from the table edges.
- **bordered(alternatesRowBackgrounds:)**: The table style that describes the behavior and appearance of a table with standard border.

## Supporting types

- **AutomaticTableStyle**: The default table style in the current context.
- **InsetTableStyle**: The table style that describes the behavior and appearance of a table with its content and selection inset from the table edges.
- **BorderedTableStyle**: The table style that describes the behavior and appearance of a table with standard border.

## Styling collection views

- **listStyle(_:)**: Sets the style for lists within this view.
- **ListStyle**: A protocol that describes the behavior and appearance of a list.
- **tableStyle(_:)**: Sets the style for tables within this view.
- **TableStyleConfiguration**: The properties of a table.
- **disclosureGroupStyle(_:)**: Sets the style for disclosure groups within this view.
- **DisclosureGroupStyle**: A type that specifies the appearance and interaction of disclosure groups within a view hierarchy.

## Conforming Types

- AutomaticTableStyle
- BorderedTableStyle
- InsetTableStyle

