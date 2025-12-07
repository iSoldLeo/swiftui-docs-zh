---
来源： https://developer.apple.com/documentation/SwiftUI/ToolbarSpacer
抓取时间： 2025-12-02T17:31:08Z
---

# ToolbarSpacer

**Structure**

工具栏中的标准空格项。

## 声明

```swift
struct ToolbarSpacer
```

## 概览

空格项可以在工具栏中的项目之间创建视觉分隔。空格可以有标准的固定大小，也可以灵活地将项目分开。

空格也可用于自定义工具栏：

```swift
ContentView()
    .toolbar(id: "main-toolbar") {
        ToolbarItem(id: "tag") {
           TagButton()
        }
        ToolbarItem(id: "share") {
           ShareButton()
        }
        ToolbarSpacer(.fixed)
        ToolbarItem(id: "more") {
           MoreButton()
        }
    }
```

空间项是可定制的，用户可以添加、删除和重新排列。如果自定义工具栏支持给定类型的间隔项，用户还可以从自定义面板中添加多份该间隔项。

## 初始化器

- **init(_:placement:)**：创建具有指定大小行为和位置的工具栏间隔项。

## 填充工具栏

- **toolbar(content:)**：用指定的项目填充工具栏或导航栏。
- **ToolbarItem**：表示可放置在工具栏或导航栏中的项目的模型。
- **ToolbarItemGroup**：表示一组`ToolbarItem`的模型，可放置在工具栏或导航栏中。
- **ToolbarItemPlacement**：定义工具栏项目位置的结构。
- **ToolbarContent**：符合类型表示可放置在工具栏不同位置的项目。
- **ToolbarContentBuilder**：从多表达式闭包构造工具栏项目集。
- **DefaultToolbarItem**：表示系统组件的工具栏项。

## 符合

- 自定义工具栏内容
- 工具栏内容


---
source: https://developer.apple.com/documentation/SwiftUI/ToolbarSpacer
crawled: 2025-12-02T17:31:08Z
---

# ToolbarSpacer

**Structure**

A standard space item in toolbars.

## Declaration

```swift
struct ToolbarSpacer
```

## Overview

A space item creates visual breaks in the toolbar between items. Spacers can have a standard fixed size or be flexible and push items apart.

Spacers can also be used in customizable toolbars:

```swift
ContentView()
    .toolbar(id: "main-toolbar") {
        ToolbarItem(id: "tag") {
           TagButton()
        }
        ToolbarItem(id: "share") {
           ShareButton()
        }
        ToolbarSpacer(.fixed)
        ToolbarItem(id: "more") {
           MoreButton()
        }
    }
```

Space items are customizable and can be added, removed, and rearranged by users. If a customizable toolbar supports a spacer of a given type, users can also add in multiple copies of that spacer from the customization panel.

## Initializers

- **init(_:placement:)**: Creates a toolbar spacer item with the specified sizing behavior and placement.

## Populating a toolbar

- **toolbar(content:)**: Populates the toolbar or navigation bar with the specified items.
- **ToolbarItem**: A model that represents an item which can be placed in the toolbar or navigation bar.
- **ToolbarItemGroup**: A model that represents a group of `ToolbarItem`s which can be placed in the toolbar or navigation bar.
- **ToolbarItemPlacement**: A structure that defines the placement of a toolbar item.
- **ToolbarContent**: Conforming types represent items that can be placed in various locations in a toolbar.
- **ToolbarContentBuilder**: Constructs a toolbar item set from multi-expression closures.
- **DefaultToolbarItem**: A toolbar item that represents a system component.

## Conforms To

- CustomizableToolbarContent
- ToolbarContent

