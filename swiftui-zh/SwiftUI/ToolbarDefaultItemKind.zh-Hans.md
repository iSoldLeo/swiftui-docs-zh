---
来源： https://developer.apple.com/documentation/SwiftUI/ToolbarDefaultItemKind
抓取时间： 2025-12-02T17:31:13Z
---

# 工具栏默认项目类型

**Structure**

`View` 默认添加的工具栏项目类型。

## 声明

```swift
struct ToolbarDefaultItemKind
```

## 概览

`View`可以添加客户希望删除或自定义的工具栏项目。可将[toolbar(removing:)](View/toolbar_removing.zh-Hans.md)修饰符传递给默认项目类型，以移除该项目。有关放置默认项目的`View` 的文档应参考用于移除项目的`ToolbarDefaultItemKind`。

## 获取默认项目类型

- **sidebarToggle**：`NavigationSplitView` 默认添加的侧边栏切换工具栏项目。

## 类型属性

- **search**：由`View/searchable(text:isPresented:placement:prompt)`修饰符添加的搜索项。
- **title**：标题栏/导航栏中显示的标题和副标题。

## 删除默认项目

- **toolbar(removing:)**：删除默认工具栏项目


---
source: https://developer.apple.com/documentation/SwiftUI/ToolbarDefaultItemKind
crawled: 2025-12-02T17:31:13Z
---

# ToolbarDefaultItemKind

**Structure**

A kind of toolbar item a `View` adds by default.

## Declaration

```swift
struct ToolbarDefaultItemKind
```

## Overview

`View`s can add toolbar items clients may wish to remove or customize. A default item kind can be passed to the [toolbar(removing:)](View/toolbar_removing.zh-Hans.md) modifier to remove the item. Documentation on the `View` placing the default item should reference the `ToolbarDefaultItemKind` used to remove the item.

## Getting the default item types

- **sidebarToggle**: The sidebar toggle toolbar item a `NavigationSplitView` adds by default.

## Type Properties

- **search**: The search item added by a `View/searchable(text:isPresented:placement:prompt)` modifier.
- **title**: The title and subtitle shown in title bar / navigation bar.

## Removing default items

- **toolbar(removing:)**: Remove a toolbar item present by default

