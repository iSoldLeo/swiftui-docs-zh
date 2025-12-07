---
来源： https://developer.apple.com/documentation/SwiftUI/ToolbarTitleMenu
抓取时间： 2025-12-02T17:31:29Z
---

# 工具栏标题菜单

**Structure**

工具栏的标题菜单。

## 声明

```swift
struct ToolbarTitleMenu<Content> where Content : View
```

## 概览

标题菜单表示可在应用程序的工具栏或导航标题所代表的内容上完成的常用功能。该菜单可由应用程序的命令填充，如 [saveItem](CommandGroupPlacement/saveItem.zh-Hans.md) 或 [printItem](CommandGroupPlacement/printItem.zh-Hans.md)。

```swift
ContentView()
    .toolbar {
        ToolbarTitleMenu()
    }
```

您可以提供自己的操作集来覆盖此行为。

```swift
ContentView()
    .toolbar {
        ToolbarTitleMenu {
            DuplicateButton()
            PrintButton()
        }
    }
```

在 iOS 和 iPadOS 中，这将构建一个菜单，点击应用程序导航栏中的导航标题即可显示该菜单。

## 创建工具栏标题菜单

- **init()**：创建工具栏标题菜单，根据应用程序命令推断操作。
- **init(content:)**：创建工具栏标题菜单。

## 设置工具栏标题菜单

- **toolbarTitleMenu(content:)**：配置工具栏标题菜单。

## 符合

- 自定义工具栏内容
- 工具栏内容


---
source: https://developer.apple.com/documentation/SwiftUI/ToolbarTitleMenu
crawled: 2025-12-02T17:31:29Z
---

# ToolbarTitleMenu

**Structure**

The title menu of a toolbar.

## Declaration

```swift
struct ToolbarTitleMenu<Content> where Content : View
```

## Overview

A title menu represents common functionality that can be done on the content represented by your app’s toolbar or navigation title. This menu may be populated from your app’s commands like [saveItem](CommandGroupPlacement/saveItem.zh-Hans.md) or [printItem](CommandGroupPlacement/printItem.zh-Hans.md).

```swift
ContentView()
    .toolbar {
        ToolbarTitleMenu()
    }
```

You can provide your own set of actions to override this behavior.

```swift
ContentView()
    .toolbar {
        ToolbarTitleMenu {
            DuplicateButton()
            PrintButton()
        }
    }
```

In iOS and iPadOS, this will construct a menu that can be presented by tapping the navigation title in the app’s navigation bar.

## Creating a toolbar title menu

- **init()**: Creates a toolbar title menu where actions are inferred from your apps commands.
- **init(content:)**: Creates a toolbar title menu.

## Setting the toolbar title menu

- **toolbarTitleMenu(content:)**: Configure the title menu of a toolbar.

## Conforms To

- CustomizableToolbarContent
- ToolbarContent

