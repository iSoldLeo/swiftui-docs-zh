--- 来源：https://developer.apple.com/documentation/swiftui/toolbarcontentbuilder

抓取时间：2025-12-04T13:08:43Z

---

# ToolbarContentBuilder

**Structure**

使用多表达式闭包构建工具栏项集。

＃＃ 宣言

```swift
@resultBuilder struct ToolbarContentBuilder
```

## 构建工具栏内容

- **buildBlock(_:)**
- **buildBlock(_:_:)**
- **buildBlock(_:_:_:)**
- **buildBlock(_:_:_:_:)**
- **buildBlock(_:_:_:_:_:)**
- **buildBlock(_:_:_:_:_:_:)**
- **buildBlock(_:_:_:_:_:_:_:)**
- **buildBlock(_:_:_:_:_:_:_:_:)**
- **buildBlock(_:_:_:_:_:_:_:_:_:)**
- **buildBlock(_:_:_:_:_:_:_:_:_:_:)**

## 构建条件工具栏内容

- **buildIf(_:)**
- **buildEither(first:)**
- **buildEither(second:)**
- **buildExpression(_:)**：在构建器中构建表达式。

- **buildLimitedAvailability(_:)**

## 填充工具栏

- **toolbar(content:)**：使用指定的项目填充工具栏或导航栏。

- **ToolbarItem**：表示可放置在工具栏或导航栏中的项目的模型。

- **ToolbarItemGroup**：表示可放置在工具栏或导航栏中的一组 `ToolbarItem` 的模型。

- **ToolbarItemPlacement**：定义工具栏项目位置的结构。

- **ToolbarContent**：符合规范的类型表示可放置在工具栏中不同位置的项目。

- **ToolbarSpacer**：工具栏中的标准空间项目。

- **DefaultToolbarItem**：工具栏项目，代表系统组件。


---
source: https://developer.apple.com/documentation/swiftui/toolbarcontentbuilder
crawled: 2025-12-04T13:08:43Z
---

# ToolbarContentBuilder

**Structure**

Constructs a toolbar item set from multi-expression closures.

## Declaration

```swift
@resultBuilder struct ToolbarContentBuilder
```

## Building toolbar content

- **buildBlock(_:)**
- **buildBlock(_:_:)**
- **buildBlock(_:_:_:)**
- **buildBlock(_:_:_:_:)**
- **buildBlock(_:_:_:_:_:)**
- **buildBlock(_:_:_:_:_:_:)**
- **buildBlock(_:_:_:_:_:_:_:)**
- **buildBlock(_:_:_:_:_:_:_:_:)**
- **buildBlock(_:_:_:_:_:_:_:_:_:)**
- **buildBlock(_:_:_:_:_:_:_:_:_:_:)**

## Building conditional toolbar content

- **buildIf(_:)**
- **buildEither(first:)**
- **buildEither(second:)**
- **buildExpression(_:)**: Builds an expression within the builder.
- **buildLimitedAvailability(_:)**

## Populating a toolbar

- **toolbar(content:)**: Populates the toolbar or navigation bar with the specified items.
- **ToolbarItem**: A model that represents an item which can be placed in the toolbar or navigation bar.
- **ToolbarItemGroup**: A model that represents a group of `ToolbarItem`s which can be placed in the toolbar or navigation bar.
- **ToolbarItemPlacement**: A structure that defines the placement of a toolbar item.
- **ToolbarContent**: Conforming types represent items that can be placed in various locations in a toolbar.
- **ToolbarSpacer**: A standard space item in toolbars.
- **DefaultToolbarItem**: A toolbar item that represents a system component.

