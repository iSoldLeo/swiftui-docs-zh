---
来源： https://developer.apple.com/documentation/swiftui/toolbarplacement
抓取时间： 2025-12-03T06:05:10Z
---

# 工具栏位置

**Structure**

工具栏的位置。

## 声明

```swift
struct ToolbarPlacement
```

## 概览

将此类型与[toolbarBackground(_:for:)](View/toolbarBackground___for.zh-Hans.md) 和 [toolbar(_:for:)](View/toolbar___for.zh-Hans.md)等修饰符结合使用，可自定义由 SwiftUI 管理的不同条形图的外观。并非所有条形图都支持所有类型的自定义。

请参阅 [ToolbarItemPlacement](ToolbarItemPlacement.zh-Hans.md)，了解您可以在这些工具栏的不同区域放置自己的控件。

## 获取位置

- **automatic**：主工具栏。
- **accessoryBar(id:)**：创建独特的附件栏位置。
- **bottomBar**：应用程序的底部工具栏。
- **bottomOrnament**：应用程序的底部工具栏：应用程序的底部装饰。
- **navigationBar**：应用程序的导航栏。
- **tabBar**：应用程序的标签栏。
- **windowToolbar**：应用程序的标签栏：包含窗口的工具栏的位置，有时也称为标题栏。

## 过时符号

- **init(id:)**：创建自定义的附件栏位置。

## 设置工具栏可见性

- **toolbar(_:for:)**：指定由 SwiftUI 管理的工具栏的可见性。
- **toolbarVisibility(_:for:)**：指定由 SwiftUI 管理的工具栏的可见性：指定由 SwiftUI 管理的条形图的可见性。
- **toolbarBackgroundVisibility(_:for:)**：指定由 SwiftUI 管理的条形图的可见性：指定由 SwiftUI 管理的条形图上背景的首选可见性。
- **ContentToolbarPlacement**：指定由 SwiftUI 管理的条形图上背景的首选可见性。


---
source: https://developer.apple.com/documentation/swiftui/toolbarplacement
crawled: 2025-12-03T06:05:10Z
---

# ToolbarPlacement

**Structure**

The placement of a toolbar.

## Declaration

```swift
struct ToolbarPlacement
```

## Overview

Use this type in conjunction with modifiers like [toolbarBackground(_:for:)](View/toolbarBackground___for.zh-Hans.md) and [toolbar(_:for:)](View/toolbar___for.zh-Hans.md) to customize the appearance of different bars managed by SwiftUI. Not all bars support all types of customizations.

See [ToolbarItemPlacement](ToolbarItemPlacement.zh-Hans.md) to learn about the different regions of these toolbars that you can place your own controls into.

## Getting placements

- **automatic**: The primary toolbar.
- **accessoryBar(id:)**: Creates a unique accessory bar placement.
- **bottomBar**: The bottom toolbar of an app.
- **bottomOrnament**: The bottom ornament of an app.
- **navigationBar**: The navigation bar of an app.
- **tabBar**: The tab bar of an app.
- **windowToolbar**: The placement for the containing window’s toolbar, sometimes referred to as the titlebar.

## Deprecated symbols

- **init(id:)**: Creates a custom accessory bar placement.

## Setting toolbar visibility

- **toolbar(_:for:)**: Specifies the visibility of a bar managed by SwiftUI.
- **toolbarVisibility(_:for:)**: Specifies the visibility of a bar managed by SwiftUI.
- **toolbarBackgroundVisibility(_:for:)**: Specifies the preferred visibility of backgrounds on a bar managed by SwiftUI.
- **ContentToolbarPlacement**

