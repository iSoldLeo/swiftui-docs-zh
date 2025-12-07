---
来源： https://developer.apple.com/documentation/SwiftUI/ToolbarItemPlacement
抓取时间： 2025-12-02T17:31:06Z
---

# 工具栏项目位置

**Structure**

定义工具栏项目位置的结构。

### 声明

```swift
struct ToolbarItemPlacement
```

## 概览

安置有两种类型：

- 语义放置（如 [principal](ToolbarItemPlacement/principal.zh-Hans.md) 和 [navigation](ToolbarItemPlacement/navigation.zh-Hans.md)）表示添加项目的意图。SwiftUI 会根据该意图及其周围环境（如当前平台）确定项目的适当位置。
- 位置放置（如 [navigationBarLeading](ToolbarItemPlacement/navigationBarLeading.zh-Hans.md)）表示项目的精确放置，通常是针对特定平台。

在 iOS、iPadOS 和 macOS 中，系统会使用工具栏的可用空间来决定在工具栏中呈现多少个项目。如果可用空间无法容纳所有项目，系统可能会创建一个溢出菜单，并将剩余项目放置在该菜单中。

### 获取语义位置

- **automatic**：系统会根据平台、尺寸类别或是否存在其他项目等多种因素自动放置项目。
- **principal**：系统将物品放在主要物品区。
- **status**：该项目表示当前上下文的状态发生变化。

## 获取特定操作的位置

- **primaryAction**：该项目代表主要操作。
- **secondaryAction**：该项目代表次要操作。
- **confirmationAction**：该项目表示模式界面的确认操作。
- **cancellationAction**：该项目表示模式界面的取消操作。
- **destructiveAction**：**destructiveAction**： 项目表示模式界面的破坏操作。
- **navigation**：该项目表示导航操作。

## 获取明确的位置

- **topBarLeading**：将项目置于顶部栏的前缘。
- **topBarTrailing**：将项目置于顶栏的后缘。
- **bottomBar**：将项目置于底部工具栏中。
- **bottomOrnament**：将项目放置在窗口下方的装饰物中。
- **keyboard**：将项目置于键盘部分。
- **accessoryBar(id:)**：创建独特的附件栏位置。

## 过时的符号

- **init(id:)**：创建自定义附件栏项目位置。
- **navigationBarLeading**：将项目置于导航栏的前缘。
- **navigationBarTrailing**：将项目置于导航栏的尾部边缘。

### 类型属性

- **largeSubtitle**：将项目置于导航栏的副标题区域。
- **largeTitle**：将项目置于导航栏的标题区域。
- **subtitle**：将项目置于导航栏的副标题区域。
- **title**：将项目置于导航栏的标题区域。

## 填充工具栏

- **toolbar(content:)**：用指定的项目填充工具栏或导航栏。
- **ToolbarItem**：表示可放置在工具栏或导航栏中的项目的模型。
- **ToolbarItemGroup**：表示一组`ToolbarItem`的模型，可放置在工具栏或导航栏中。
- **ToolbarContent**：符合类型表示可放置在工具栏不同位置的项目。
- **ToolbarContentBuilder**：从多表达式闭包构造工具栏项目集。
- **ToolbarSpacer**：工具栏中的标准空格项。
- **DefaultToolbarItem**：工具栏中的标准空格项：表示系统组件的工具栏项目。


---
source: https://developer.apple.com/documentation/SwiftUI/ToolbarItemPlacement
crawled: 2025-12-02T17:31:06Z
---

# ToolbarItemPlacement

**Structure**

A structure that defines the placement of a toolbar item.

## Declaration

```swift
struct ToolbarItemPlacement
```

## Overview

There are two types of placements:

- Semantic placements, such as [principal](ToolbarItemPlacement/principal.zh-Hans.md) and [navigation](ToolbarItemPlacement/navigation.zh-Hans.md), denote the intent of the item being added. SwiftUI determines the appropriate placement for the item based on this intent and its surrounding context, like the current platform.
- Positional placements, such as [navigationBarLeading](ToolbarItemPlacement/navigationBarLeading.zh-Hans.md), denote a precise placement for the item, usually for a particular platform.

In iOS, iPadOS, and macOS, the system uses the space available to the toolbar when determining how many items to render in the toolbar. If not all items fit in the available space, an overflow menu may be created and remaining items placed in that menu.

## Getting semantic placement

- **automatic**: The system places the item automatically, depending on many factors including the platform, size class, or presence of other items.
- **principal**: The system places the item in the principal item section.
- **status**: The item represents a change in status for the current context.

## Getting placement for specific actions

- **primaryAction**: The item represents a primary action.
- **secondaryAction**: The item represents a secondary action.
- **confirmationAction**: The item represents a confirmation action for a modal interface.
- **cancellationAction**: The item represents a cancellation action for a modal interface.
- **destructiveAction**: The item represents a destructive action for a modal interface.
- **navigation**: The item represents a navigation action.

## Getting explicit placement

- **topBarLeading**: Places the item in the leading edge of the top bar.
- **topBarTrailing**: Places the item in the trailing edge of the top bar.
- **bottomBar**: Places the item in the bottom toolbar.
- **bottomOrnament**: Places the item in an ornament under the window.
- **keyboard**: The item is placed in the keyboard section.
- **accessoryBar(id:)**: Creates a unique accessory bar placement.

## Deprecated symbols

- **init(id:)**: Creates a custom accessory bar item placement.
- **navigationBarLeading**: Places the item in the leading edge of the navigation bar.
- **navigationBarTrailing**: Places the item in the trailing edge of the navigation bar.

## Type Properties

- **largeSubtitle**: Places the item in the subtitle area of the navigation bar.
- **largeTitle**: Places the item in the title area of the navigation bar.
- **subtitle**: Places the item in the subtitle area of the navigation bar.
- **title**: Places the item in the title area of the navigation bar.

## Populating a toolbar

- **toolbar(content:)**: Populates the toolbar or navigation bar with the specified items.
- **ToolbarItem**: A model that represents an item which can be placed in the toolbar or navigation bar.
- **ToolbarItemGroup**: A model that represents a group of `ToolbarItem`s which can be placed in the toolbar or navigation bar.
- **ToolbarContent**: Conforming types represent items that can be placed in various locations in a toolbar.
- **ToolbarContentBuilder**: Constructs a toolbar item set from multi-expression closures.
- **ToolbarSpacer**: A standard space item in toolbars.
- **DefaultToolbarItem**: A toolbar item that represents a system component.

