---
来源： https://developer.apple.com/documentation/SwiftUI/TextEditingCommands
抓取时间： 2025-12-02T17:36:25Z
---

# 文本编辑命令

**Structure**

一组用于搜索、编辑和转换文本选区的内置命令。

## 声明

```swift
struct TextEditingCommands
```

## 概览

这些命令是可选的，可以通过向 `Scene.commands(_:)` 修改器传递该类型的值来明确请求。

## 创建命令组

- **init()**：描述内置文本编辑命令的新值。

## 获取内置命令组

- **SidebarCommands**：用于操作窗口边栏的内置命令集。
- **TextFormattingCommands**：用于转换应用于文本选区的样式的内置命令集。
- **ToolbarCommands**：用于操作窗口工具栏的内置命令集。
- **ImportFromDevicesCommands**：用于从附近设备导入内容的内置命令集。
- **InspectorCommands**：用于操作检查器的内置命令集。
- **EmptyCommands**：一组空命令。

## 符合

- 命令


---
source: https://developer.apple.com/documentation/SwiftUI/TextEditingCommands
crawled: 2025-12-02T17:36:25Z
---

# TextEditingCommands

**Structure**

A built-in group of commands for searching, editing, and transforming selections of text.

## Declaration

```swift
struct TextEditingCommands
```

## Overview

These commands are optional and can be explicitly requested by passing a value of this type to the `Scene.commands(_:)` modifier.

## Creating the command group

- **init()**: A new value describing the built-in text-editing commands.

## Getting built-in command groups

- **SidebarCommands**: A built-in set of commands for manipulating window sidebars.
- **TextFormattingCommands**: A built-in set of commands for transforming the styles applied to selections of text.
- **ToolbarCommands**: A built-in set of commands for manipulating window toolbars.
- **ImportFromDevicesCommands**: A built-in set of commands that enables importing content from nearby devices.
- **InspectorCommands**: A built-in set of commands for manipulating inspectors.
- **EmptyCommands**: An empty group of commands.

## Conforms To

- Commands

