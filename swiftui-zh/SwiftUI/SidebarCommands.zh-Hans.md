--- 来源：https://developer.apple.com/documentation/SwiftUI/SidebarCommands
抓取时间：2025-12-02T17:36:24Z

---

# SidebarCommands

**Structure**

一组用于操作窗口侧边栏的内置命令。

## 声明

```swift
struct SidebarCommands
```

## 概述

这些命令是可选的，可以通过将此类型的值传递给 [commands(content:)](scene/commands_content.zh-Hans.md) 修饰符来显式请求。

## 创建命令组

- **init()**：描述内置侧边栏相关命令的新值。

## 获取内置命令组

- **TextEditingCommands**：用于搜索、编辑和转换选定文本的内置命令组。

- **TextFormattingCommands**：用于转换应用于选定文本的样式的内置命令集。

- **ToolbarCommands**：用于操作窗口工具栏的内置命令集。

- **ImportFromDevicesCommands**：用于从附近设备导入内容的内置命令集。

- **InspectorCommands**：用于操作检查器的内置命令集。

- **EmptyCommands**：一个空的命令组。

## 符合以下规范

- 命令


---
source: https://developer.apple.com/documentation/SwiftUI/SidebarCommands
crawled: 2025-12-02T17:36:24Z
---

# SidebarCommands

**Structure**

A built-in set of commands for manipulating window sidebars.

## Declaration

```swift
struct SidebarCommands
```

## Overview

These commands are optional and can be explicitly requested by passing a value of this type to the [commands(content:)](scene/commands_content.zh-Hans.md) modifier.

## Creating the command group

- **init()**: A new value describing the built-in sidebar-related commands.

## Getting built-in command groups

- **TextEditingCommands**: A built-in group of commands for searching, editing, and transforming selections of text.
- **TextFormattingCommands**: A built-in set of commands for transforming the styles applied to selections of text.
- **ToolbarCommands**: A built-in set of commands for manipulating window toolbars.
- **ImportFromDevicesCommands**: A built-in set of commands that enables importing content from nearby devices.
- **InspectorCommands**: A built-in set of commands for manipulating inspectors.
- **EmptyCommands**: An empty group of commands.

## Conforms To

- Commands

