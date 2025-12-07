---
来源： https://developer.apple.com/documentation/SwiftUI/ToolbarItemGroup
抓取时间： 2025-12-02T17:31:05Z
---

# 工具栏项目组

**Structure**

表示一组`ToolbarItem`的模型，可放置在工具栏或导航栏中。

### 声明

```swift
struct ToolbarItemGroup<Content> where Content : View
```

## 创建工具栏项目组

- **init(placement:content:)**：创建具有指定位置和内容的工具栏项目组。
- **init(placement:content:label:)**：以指定的位置、内容和描述该内容的标签创建工具栏项目组。

### 支持类型

- **LabeledToolbarItemGroupContent**：视图，表示带有指定标签的工具栏项目组的视图。

## 填充工具栏

- **toolbar(content:)**：用指定的项目填充工具栏或导航栏。
- **ToolbarItem**：表示可放置在工具栏或导航栏中的项目的模型。
- **ToolbarItemPlacement**：定义工具栏项目位置的结构。
- **ToolbarContent**：符合类型表示可放置在工具栏不同位置的项目。
- **ToolbarContentBuilder**：从多表达式闭包构造工具栏项目集。
- **ToolbarSpacer**：工具栏中的标准空格项。
- **DefaultToolbarItem**：工具栏中的标准空格项：表示系统组件的工具栏项目。

## 符合

- 工具栏内容


---
source: https://developer.apple.com/documentation/SwiftUI/ToolbarItemGroup
crawled: 2025-12-02T17:31:05Z
---

# ToolbarItemGroup

**Structure**

A model that represents a group of `ToolbarItem`s which can be placed in the toolbar or navigation bar.

## Declaration

```swift
struct ToolbarItemGroup<Content> where Content : View
```

## Creating a toolbar item group

- **init(placement:content:)**: Creates a toolbar item group with a specified placement and content.
- **init(placement:content:label:)**: Creates a toolbar item group with the specified placement, content, and a label describing that content.

## Supporting types

- **LabeledToolbarItemGroupContent**: A view that represents the view of a toolbar item group with a specified label.

## Populating a toolbar

- **toolbar(content:)**: Populates the toolbar or navigation bar with the specified items.
- **ToolbarItem**: A model that represents an item which can be placed in the toolbar or navigation bar.
- **ToolbarItemPlacement**: A structure that defines the placement of a toolbar item.
- **ToolbarContent**: Conforming types represent items that can be placed in various locations in a toolbar.
- **ToolbarContentBuilder**: Constructs a toolbar item set from multi-expression closures.
- **ToolbarSpacer**: A standard space item in toolbars.
- **DefaultToolbarItem**: A toolbar item that represents a system component.

## Conforms To

- ToolbarContent

