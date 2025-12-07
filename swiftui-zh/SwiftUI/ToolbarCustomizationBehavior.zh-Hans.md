--- 来源：https://developer.apple.com/documentation/SwiftUI/ToolbarCustomizationBehavior
抓取时间：2025-12-02T17:31:11Z
---

# ToolbarCustomizationBehavior

**Structure**

可自定义工具栏内容的自定义行为。

## 声明

```swift
struct ToolbarCustomizationBehavior
```

## 概述

可自定义工具栏内容支持不同类型的自定义行为。例如，某些可自定义内容可能无法被用户移除。某些内容可能放置在支持整体自定义的工具栏中，但不支持针对该特定内容的自定义。

请将此类型与 [customizationBehavior(_:)](CustomizableToolbarContent/customizationBehavior.zh-Hans.md) 修饰符结合使用。

## 获取自定义行为

- **default**：默认自定义行为。

- **disabled**：禁用自定义行为。

- **reorderable**：可重新排序的自定义行为。

## 填充可自定义工具栏

- **toolbar(id:content:)**：使用指定的项目填充工具栏或导航栏，允许用户进行自定义。

- **CustomizableToolbarContent**：符合规范的类型表示可以放置在可自定义工具栏中不同位置的项目。

- **ToolbarCustomizationOptions**：影响可自定义工具栏内容默认自定义行为的选项。

- **SearchToolbarBehavior**：工具栏中搜索字段的行为。

## 符合以下规范

- Sendable

- SendableMetatype


---
source: https://developer.apple.com/documentation/SwiftUI/ToolbarCustomizationBehavior
crawled: 2025-12-02T17:31:11Z
---

# ToolbarCustomizationBehavior

**Structure**

The customization behavior of customizable toolbar content.

## Declaration

```swift
struct ToolbarCustomizationBehavior
```

## Overview

Customizable toolbar content support different types of customization behaviors. For example, some customizable content may not be removed by the user. Some content may be placed in a toolbar that supports customization overall, but not for that particular content.

Use this type in conjunction with the [customizationBehavior(_:)](CustomizableToolbarContent/customizationBehavior.zh-Hans.md) modifier.

## Getting customization behaviors

- **default**: The default customization behavior.
- **disabled**: The disabled customization behavior.
- **reorderable**: The reorderable customization behavior.

## Populating a customizable toolbar

- **toolbar(id:content:)**: Populates the toolbar or navigation bar with the specified items, allowing for user customization.
- **CustomizableToolbarContent**: Conforming types represent items that can be placed in various locations in a customizable toolbar.
- **ToolbarCustomizationOptions**: Options that influence the default customization behavior of customizable toolbar content.
- **SearchToolbarBehavior**: The behavior of a search field in a toolbar.

## Conforms To

- Sendable
- SendableMetatype

