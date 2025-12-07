---
来源： https://developer.apple.com/documentation/SwiftUI/ToolbarCommands
抓取时间： 2025-12-02T17:36:27Z
---

# 工具栏命令

**Structure**

用于操作窗口工具栏的内置命令集。

## 声明

```swift
struct ToolbarCommands
```

## 概览

这些命令是可选的，可以通过向 [commands(content:)](scene/commands_content.zh-Hans.md) 修饰符传递该类型的值来明确请求。

## 创建命令组

- **init()**：描述内置工具栏相关命令的新值。

## 获取内置命令组

- **SidebarCommands**：用于操作窗口边栏的内置命令集。
- **TextEditingCommands**：用于搜索、编辑和转换文本选区的内置命令集。
- **TextFormattingCommands**：用于转换应用于文本选区的样式的内置命令集。
- **ImportFromDevicesCommands**：用于从附近设备导入内容的内置命令集。
- **InspectorCommands**：用于操作检查器的内置命令集。
- **EmptyCommands**：一组空命令。

## 符合

- 命令


---
source: https://developer.apple.com/documentation/SwiftUI/ToolbarCommands
crawled: 2025-12-02T17:36:27Z
---

# ToolbarCommands

**Structure**

A built-in set of commands for manipulating window toolbars.

## Declaration

```swift
struct ToolbarCommands
```

## Overview

These commands are optional and can be explicitly requested by passing a value of this type to the [commands(content:)](scene/commands_content.zh-Hans.md) modifier.

## Creating the command group

- **init()**: A new value describing the built-in toolbar-related commands.

## Getting built-in command groups

- **SidebarCommands**: A built-in set of commands for manipulating window sidebars.
- **TextEditingCommands**: A built-in group of commands for searching, editing, and transforming selections of text.
- **TextFormattingCommands**: A built-in set of commands for transforming the styles applied to selections of text.
- **ImportFromDevicesCommands**: A built-in set of commands that enables importing content from nearby devices.
- **InspectorCommands**: A built-in set of commands for manipulating inspectors.
- **EmptyCommands**: An empty group of commands.

## Conforms To

- Commands

