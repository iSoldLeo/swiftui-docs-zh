--- 来源：https://developer.apple.com/documentation/SwiftUI/DefaultToolbarItem
抓取时间：2025-12-02T17:31:08Z

---

# DefaultToolbarItem

**Structure**

代表系统组件的工具栏项。

## 声明

```swift
struct DefaultToolbarItem
```

## 概述

将此项放置在工具栏中，以控制系统提供的项（例如搜索）的位置。

## 初始化器

- **init(kind:placement:)**：根据给定的 `placement` 处的 `ToolbarDefaultItemKind` 创建系统定义的工具栏项。

## 填充工具栏

- **toolbar(content:)**：使用指定的项填充工具栏或导航栏。

- **ToolbarItem**：表示可放置在工具栏或导航栏中的项目的模型。

- **ToolbarItemGroup**：表示可放置在工具栏或导航栏中的一组 `ToolbarItem` 的模型。

- **ToolbarItemPlacement**：定义工具栏项目位置的结构。

- **ToolbarContent**：符合规范的类型表示可放置在工具栏中不同位置的项目。

- **ToolbarContentBuilder**：从多表达式闭包构造工具栏项目集。

- **ToolbarSpacer**：工具栏中的标准空间项目。

## 符合以下规范

- ToolbarContent


---
source: https://developer.apple.com/documentation/SwiftUI/DefaultToolbarItem
crawled: 2025-12-02T17:31:08Z
---

# DefaultToolbarItem

**Structure**

A toolbar item that represents a system component.

## Declaration

```swift
struct DefaultToolbarItem
```

## Overview

Place this item in your toolbar to control where the system-provided item, like search, will be positioned.

## Initializers

- **init(kind:placement:)**: Creates a system-defined toolbar item from a `ToolbarDefaultItemKind` at the given `placement`.

## Populating a toolbar

- **toolbar(content:)**: Populates the toolbar or navigation bar with the specified items.
- **ToolbarItem**: A model that represents an item which can be placed in the toolbar or navigation bar.
- **ToolbarItemGroup**: A model that represents a group of `ToolbarItem`s which can be placed in the toolbar or navigation bar.
- **ToolbarItemPlacement**: A structure that defines the placement of a toolbar item.
- **ToolbarContent**: Conforming types represent items that can be placed in various locations in a toolbar.
- **ToolbarContentBuilder**: Constructs a toolbar item set from multi-expression closures.
- **ToolbarSpacer**: A standard space item in toolbars.

## Conforms To

- ToolbarContent

