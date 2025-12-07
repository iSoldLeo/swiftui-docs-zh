--- 来源：https://developer.apple.com/documentation/SwiftUI/TabPlacement
抓取时间：2025-12-02T17:29:56Z

---

# TabPlacement

**Structure**

标签页的显示位置。

## 声明

```swift
struct TabPlacement
```

## 概述

并非所有 `TabView` 样式都支持所有位置。

## 类型属性

- **automatic**：默认标签页位置。

- **pinned**：固定标签页的位置。

- **sidebarOnly**：侧边栏标签页的位置。

## 配置标签页

- **sectionActions(content:)**：向选项卡添加自定义操作。 - **TabContentBuilder**：用于构建支持程序化选择的选项卡视图的选项卡的结果构建器。此构建器要求选项卡视图中的所有选项卡具有相同的选择类型。

- **TabContent**：为选项卡视图中可通过程序选择的选项卡提供内容的类型。

- **AnyTabContent**：擦除选项卡内容的类型。

## 符合以下规范

- Equatable

- Hashable


---
source: https://developer.apple.com/documentation/SwiftUI/TabPlacement
crawled: 2025-12-02T17:29:56Z
---

# TabPlacement

**Structure**

A place that a tab can appear.

## Declaration

```swift
struct TabPlacement
```

## Overview

Not all `TabView` styles support all placements.

## Type Properties

- **automatic**: The default tab location.
- **pinned**: The pinned tab placement location.
- **sidebarOnly**: The sidebar tab placement location.

## Configuring a tab

- **sectionActions(content:)**: Adds custom actions to a section.
- **TabContentBuilder**: A result builder that constructs tabs for a tab view that supports programmatic selection. This builder requires that all tabs in the tab view have the same selection type.
- **TabContent**: A type that provides content for programmatically selectable tabs in a tab view.
- **AnyTabContent**: Type erased tab content.

## Conforms To

- Equatable
- Hashable

