--- 来源：https://developer.apple.com/documentation/SwiftUI/ToolbarItem
抓取时间：2025-12-02T17:31:04Z

---

# ToolbarItem

**Structure**

一个表示可放置在工具栏或导航栏中的项目的模型。

## 声明

```swift
struct ToolbarItem<ID, Content> where Content : View
```

## 创建工具栏项目

- **init(placement:content:)**：创建具有指定位置和内容的工具栏项目。

- **init(id:placement:content:)**：创建具有指定位置和内容的工具栏项目，并允许用户自定义。

- **init(id:placement:showsByDefault:content:)**：创建具有指定位置和内容的工具栏项目，并允许用户自定义。

## 填充工具栏

- **toolbar(content:)**：使用指定的项目填充工具栏或导航栏。

- **ToolbarItemGroup**：表示一组可放置在工具栏或导航栏中的 `ToolbarItem` 的模型。

- **ToolbarItemPlacement**：定义工具栏项目位置的结构。

- **ToolbarContent**：符合规范的类型表示可放置在工具栏中不同位置的项目。

- **ToolbarContentBuilder**：从多表达式闭包构造工具栏项目集。

- **ToolbarSpacer**：工具栏中的标准空间项目。

- **DefaultToolbarItem**：表示系统组件的工具栏项目。

## 符合以下要求

- 可复制

- 可自定义工具栏内容

- 可识别

- 工具栏内容


---
source: https://developer.apple.com/documentation/SwiftUI/ToolbarItem
crawled: 2025-12-02T17:31:04Z
---

# ToolbarItem

**Structure**

A model that represents an item which can be placed in the toolbar or navigation bar.

## Declaration

```swift
struct ToolbarItem<ID, Content> where Content : View
```

## Creating a toolbar item

- **init(placement:content:)**: Creates a toolbar item with the specified placement and content.
- **init(id:placement:content:)**: Creates a toolbar item with the specified placement and content, which allows for user customization.
- **init(id:placement:showsByDefault:content:)**: Creates a toolbar item with the specified placement and content, which allows for user customization.

## Populating a toolbar

- **toolbar(content:)**: Populates the toolbar or navigation bar with the specified items.
- **ToolbarItemGroup**: A model that represents a group of `ToolbarItem`s which can be placed in the toolbar or navigation bar.
- **ToolbarItemPlacement**: A structure that defines the placement of a toolbar item.
- **ToolbarContent**: Conforming types represent items that can be placed in various locations in a toolbar.
- **ToolbarContentBuilder**: Constructs a toolbar item set from multi-expression closures.
- **ToolbarSpacer**: A standard space item in toolbars.
- **DefaultToolbarItem**: A toolbar item that represents a system component.

## Conforms To

- Copyable
- CustomizableToolbarContent
- Identifiable
- ToolbarContent

