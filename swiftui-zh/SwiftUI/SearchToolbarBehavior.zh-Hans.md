---
来源： https://developer.apple.com/documentation/SwiftUI/SearchToolbarBehavior
抓取时间： 2025-12-02T17:31:12Z
---

# 搜索工具栏行为

**Structure**

工具栏中搜索字段的行为。

## 声明

```swift
struct SearchToolbarBehavior
```

## 概览

该类型与[searchToolbarBehavior(_:)](View/searchToolbarBehavior.zh-Hans.md)修饰符结合使用。

### 类型属性

- **automatic**：自动行为。
- **minimize**：搜索工具栏行为，倾向于将搜索字段渲染为类似按钮的控件。

## 填充自定义工具栏

- **toolbar(id:content:)**：用指定的项目填充工具栏或导航栏，允许用户自定义。
- **CustomizableToolbarContent**：符合类型表示可放置在自定义工具栏不同位置的项目。
- **ToolbarCustomizationBehavior**：自定义工具栏内容的自定义行为。
- **ToolbarCustomizationOptions**：影响可定制工具栏内容默认定制行为的选项。

## 符合

- 等价
- 可散列
- 可发送
- 可发送元类型


---
source: https://developer.apple.com/documentation/SwiftUI/SearchToolbarBehavior
crawled: 2025-12-02T17:31:12Z
---

# SearchToolbarBehavior

**Structure**

The behavior of a search field in a toolbar.

## Declaration

```swift
struct SearchToolbarBehavior
```

## Overview

Use this type in combination with the [searchToolbarBehavior(_:)](View/searchToolbarBehavior.zh-Hans.md) modifier.

## Type Properties

- **automatic**: The automatic behavior.
- **minimize**: A search toolbar behavior that prefers rendering a search field as a button-like control.

## Populating a customizable toolbar

- **toolbar(id:content:)**: Populates the toolbar or navigation bar with the specified items, allowing for user customization.
- **CustomizableToolbarContent**: Conforming types represent items that can be placed in various locations in a customizable toolbar.
- **ToolbarCustomizationBehavior**: The customization behavior of customizable toolbar content.
- **ToolbarCustomizationOptions**: Options that influence the default customization behavior of customizable toolbar content.

## Conforms To

- Equatable
- Hashable
- Sendable
- SendableMetatype

