---
来源： https://developer.apple.com/documentation/SwiftUI/InspectorCommands
抓取时间： 2025-12-02T17:36:28Z
---

# 检查员命令

**Structure**

用于操作检查器的内置命令集。

## 声明

```swift
struct InspectorCommands
```

## 概览

`InspectorCommands`包含一条命令，用于使用键盘快捷键 Control-Command-I 切换检查器的显示状态。

这些命令是可选的，可以通过向 [commands(content:)](scene/commands_content.zh-Hans.md) 修改器传递该类型的值来明确请求：

```swift
@State var presented = true
WindowGroup {
    MainView()
        .inspector(isPresented: $presented) {
            InspectorView()
        }
}
.commands {
    InspectorCommands()
}
```

## 创建命令

- **init()**：描述内置检查器相关命令的新值。

## 获取内置命令组

- **SidebarCommands**：用于操作窗口边栏的内置命令集。
- **TextEditingCommands**：用于搜索、编辑和转换文本选区的内置命令集。
- **TextFormattingCommands**：用于转换应用于文本选区的样式的内置命令集。
- **ToolbarCommands**：用于操作窗口工具栏的内置命令集。
- **ImportFromDevicesCommands**：用于从附近设备导入内容的内置命令集。
- **EmptyCommands**：一组空命令。

## 符合

- 命令


---
source: https://developer.apple.com/documentation/SwiftUI/InspectorCommands
crawled: 2025-12-02T17:36:28Z
---

# InspectorCommands

**Structure**

A built-in set of commands for manipulating inspectors.

## Declaration

```swift
struct InspectorCommands
```

## Overview

`InspectorCommands` include a command for toggling the presented state of the inspector with a keyboard shortcut of Control-Command-I.

These commands are optional and can be explicitly requested by passing a value of this type to the [commands(content:)](scene/commands_content.zh-Hans.md) modifier:

```swift
@State var presented = true
WindowGroup {
    MainView()
        .inspector(isPresented: $presented) {
            InspectorView()
        }
}
.commands {
    InspectorCommands()
}
```

## Creating a command

- **init()**: A new value describing the built-in inspector-related commands.

## Getting built-in command groups

- **SidebarCommands**: A built-in set of commands for manipulating window sidebars.
- **TextEditingCommands**: A built-in group of commands for searching, editing, and transforming selections of text.
- **TextFormattingCommands**: A built-in set of commands for transforming the styles applied to selections of text.
- **ToolbarCommands**: A built-in set of commands for manipulating window toolbars.
- **ImportFromDevicesCommands**: A built-in set of commands that enables importing content from nearby devices.
- **EmptyCommands**: An empty group of commands.

## Conforms To

- Commands

