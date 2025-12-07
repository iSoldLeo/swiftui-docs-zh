--- 来源：https://developer.apple.com/documentation/SwiftUI/ToolbarCustomizationOptions
抓取时间：2025-12-02T17:31:11Z

---

# ToolbarCustomizationOptions

**Structure**

影响可自定义工具栏内容默认自定义行为的选项。

## 声明

```swift
struct ToolbarCustomizationOptions
```

## 概述

此类型需与 [defaultCustomization(_:options:)](CustomizableToolbarContent/defaultCustomization___options.zh-Hans.md) 修饰符结合使用。

## 获取自定义选项

- **alwaysAvailable**：配置默认可自定义工具栏内容，使其始终显示在工具栏中。

## 填充可自定义工具栏

- **toolbar(id:content:)**：使用指定的项目填充工具栏或导航栏，允许用户进行自定义。

- **CustomizableToolbarContent**：符合规范的类型表示可以放置在可自定义工具栏中不同位置的项。

- **ToolbarCustomizationBehavior**：可自定义工具栏内容的自定义行为。

- **SearchToolbarBehavior**：工具栏中搜索字段的行为。

## 符合以下规范

- Equatable

- ExpressibleByArrayLiteral

- OptionSet

- RawRepresentable

- Sendable

- SendableMetatype

- SetAlgebra


---
source: https://developer.apple.com/documentation/SwiftUI/ToolbarCustomizationOptions
crawled: 2025-12-02T17:31:11Z
---

# ToolbarCustomizationOptions

**Structure**

Options that influence the default customization behavior of customizable toolbar content.

## Declaration

```swift
struct ToolbarCustomizationOptions
```

## Overview

Use this type in conjunction with the [defaultCustomization(_:options:)](CustomizableToolbarContent/defaultCustomization___options.zh-Hans.md) modifier.

## Getting customization options

- **alwaysAvailable**: Configures default customizable toolbar content to always be present in the toolbar.

## Populating a customizable toolbar

- **toolbar(id:content:)**: Populates the toolbar or navigation bar with the specified items, allowing for user customization.
- **CustomizableToolbarContent**: Conforming types represent items that can be placed in various locations in a customizable toolbar.
- **ToolbarCustomizationBehavior**: The customization behavior of customizable toolbar content.
- **SearchToolbarBehavior**: The behavior of a search field in a toolbar.

## Conforms To

- Equatable
- ExpressibleByArrayLiteral
- OptionSet
- RawRepresentable
- Sendable
- SendableMetatype
- SetAlgebra

