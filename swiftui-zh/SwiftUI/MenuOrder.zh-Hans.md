--- 来源：https://developer.apple.com/documentation/SwiftUI/MenuOrder
抓取时间：2025-12-02T17:36:34Z

---

# 菜单顺序

**Structure**

菜单内容的呈现顺序。

## 声明

```swift
struct MenuOrder
```

## 概述

您可以使用 [menuOrder(_:)](View/menuOrder.zh-Hans.md) 视图修饰符配置首选菜单顺序。

## 获取菜单顺序

- **automatic**：系统为当前上下文选择的菜单顺序。

- **fixed**：菜单项从上到下排序。

- **priority**：将第一个菜单项保持在用户交互点附近。

## 设置菜单项顺序

- **menuOrder(_:)**：设置此视图中菜单项的首选顺序。

- **menuOrder**：此视图中菜单项的首选顺序。

## 符合以下标准

- Equatable

- Hashable

- Sendable

- SendableMetatype


---
source: https://developer.apple.com/documentation/SwiftUI/MenuOrder
crawled: 2025-12-02T17:36:34Z
---

# MenuOrder

**Structure**

The order in which a menu presents its content.

## Declaration

```swift
struct MenuOrder
```

## Overview

You can configure the preferred menu order using the [menuOrder(_:)](View/menuOrder.zh-Hans.md) view modifier.

## Getting menu orders

- **automatic**: The ordering of the menu chosen by the system for the current context.
- **fixed**: Order items from top to bottom.
- **priority**: Keep the first items closest to user’s interaction point.

## Setting a preferred order

- **menuOrder(_:)**: Sets the preferred order of items for menus presented from this view.
- **menuOrder**: The preferred order of items for menus presented from this view.

## Conforms To

- Equatable
- Hashable
- Sendable
- SendableMetatype

