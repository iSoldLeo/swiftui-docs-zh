--- 来源：https://developer.apple.com/documentation/swiftui/contextmenu

抓取时间：2025-12-03T06:23:59Z

---

# 上下文菜单

**Structure**

用于存放视图的容器，这些视图会以菜单项的形式显示在上下文菜单中。

## 声明

```swift
struct ContextMenu<MenuItems> where MenuItems : View
```

## 概述

上下文菜单视图允许您显示一个特定于当前情境的菜单，以便执行与当前任务相关的操作。

您可以通过以下方式创建上下文菜单：首先定义一个 `ContextMenu` 容器，其中包含表示用户可以执行的操作的控件；然后使用 [contextMenu(_:)](View/contextMenu.zh-Hans.md) 视图修饰符将菜单应用到视图。

以下示例创建了一个包含两个菜单项的上下文菜单容器，并将其应用到 [Text](Text.zh-Hans.md) 视图。布尔值 `shouldShowMenu`（默认为 true）控制上下文菜单的可用性：

```swift
private let menuItems = ContextMenu {
    Button {
        // Add this item to a list of favorites.
    } label: {
        Label("Add to Favorites", systemImage: "heart")
    }
    Button {
        // Open Maps and center it on this item.
    } label: {
        Label("Show in Maps", systemImage: "mappin")
    }
}

private struct ContextMenuMenuItems: View {
    @State private var shouldShowMenu = true

    var body: some View {
        Text("Turtle Rock")
            .contextMenu(shouldShowMenu ? menuItems : nil)
    }
}
```

## 创建上下文菜单

- **init(menuItems:)**：创建上下文菜单。

## 已弃用类型

- **MenuButton**：按钮，按下时显示包含选项列表的菜单。

- **PullDownButton**


---
source: https://developer.apple.com/documentation/swiftui/contextmenu
crawled: 2025-12-03T06:23:59Z
---

# ContextMenu

**Structure**

A container for views that you present as menu items in a context menu.

## Declaration

```swift
struct ContextMenu<MenuItems> where MenuItems : View
```

## Overview

A context menu view allows you to present a situationally specific menu that enables taking actions relevant to the current task.

You can create a context menu by first defining a `ContextMenu` container with the controls that represent the actions people can take, and then using the [contextMenu(_:)](View/contextMenu.zh-Hans.md) view modifier to apply the menu to a view.

The example below creates and applies a two item context menu container to a [Text](Text.zh-Hans.md) view. The Boolean value `shouldShowMenu`, which defaults to true, controls the availability of context menu:

```swift
private let menuItems = ContextMenu {
    Button {
        // Add this item to a list of favorites.
    } label: {
        Label("Add to Favorites", systemImage: "heart")
    }
    Button {
        // Open Maps and center it on this item.
    } label: {
        Label("Show in Maps", systemImage: "mappin")
    }
}

private struct ContextMenuMenuItems: View {
    @State private var shouldShowMenu = true

    var body: some View {
        Text("Turtle Rock")
            .contextMenu(shouldShowMenu ? menuItems : nil)
    }
}
```



## Creating a context menu

- **init(menuItems:)**: Creates a context menu.

## Deprecated types

- **MenuButton**: A button that displays a menu containing a list of choices when pressed.
- **PullDownButton**

