---

来源：https://developer.apple.com/documentation/SwiftUI/ImportFromDevicesCommands
抓取时间：2025-12-02T17:36:28Z

---

# ImportFromDevicesCommands

**Structure**

一组内置命令，用于从附近的设备导入内容。

## 声明

```swift
struct ImportFromDevicesCommands
```

## 概述

这组命令会根据附近的设备及其功能（例如拍照或扫描文档）添加项目。视图可以使用 [importsItemProviders(_:onImport:)](View/importsItemProviders___onImport.zh-Hans.md) 修饰符接收从这些菜单项导入的内容。

这些命令是可选的，您可以通过将此类型的值传递给 [commands(content:)](scene/commands_content.zh-Hans.md) 修饰符来显式请求它们。

## 创建命令组

- **init()**：创建新的设备导入命令集。

## 获取内置命令组

- **SidebarCommands**：用于操作窗口侧边栏的内置命令集。

- **TextEditingCommands**：用于搜索、编辑和转换选定文本的内置命令组。

- **TextFormattingCommands**：用于转换应用于选定文本的样式的内置命令集。

- **ToolbarCommands**：用于操作窗口工具栏的内置命令集。

- **InspectorCommands**：用于操作检查器的内置命令集。

- **EmptyCommands**：一个空的命令组。

## 符合以下规则

- 命令


---
source: https://developer.apple.com/documentation/SwiftUI/ImportFromDevicesCommands
crawled: 2025-12-02T17:36:28Z
---

# ImportFromDevicesCommands

**Structure**

A built-in set of commands that enables importing content from nearby devices.

## Declaration

```swift
struct ImportFromDevicesCommands
```

## Overview

This set of commands adds items based on nearby devices and capabilities, like taking photos or scanning documents. Views can receive imported content from these menu items by using the [importsItemProviders(_:onImport:)](View/importsItemProviders___onImport.zh-Hans.md) modifier.

These commands are optional and you can explicitly request them by passing a value of this type to the [commands(content:)](scene/commands_content.zh-Hans.md) modifier.

## Creating the command group

- **init()**: Creates a new set of device import commands.

## Getting built-in command groups

- **SidebarCommands**: A built-in set of commands for manipulating window sidebars.
- **TextEditingCommands**: A built-in group of commands for searching, editing, and transforming selections of text.
- **TextFormattingCommands**: A built-in set of commands for transforming the styles applied to selections of text.
- **ToolbarCommands**: A built-in set of commands for manipulating window toolbars.
- **InspectorCommands**: A built-in set of commands for manipulating inspectors.
- **EmptyCommands**: An empty group of commands.

## Conforms To

- Commands

