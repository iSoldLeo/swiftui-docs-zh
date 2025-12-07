--- 来源：https://developer.apple.com/documentation/SwiftUI/TableColumnCustomizationBehavior
抓取时间：2025-12-02T17:39:58Z

---

# TableColumnCustomizationBehavior

**Structure**

表格可以向用户提供的列自定义行为集合。

## 声明

```swift
struct TableColumnCustomizationBehavior
```

## 概述

此值将提供给 [disabledCustomizationBehavior(_:)](TableColumnContent/disabledCustomizationBehavior.zh-Hans.md)。

将这些值中的任何一个设置为 `disabledCustomizationBehavior(_:)` 在 iOS 上都不会产生任何效果。

## 获取自定义行为

- **all**：所有自定义行为。

- **reorder**：允许用户重新排列列的行为。

- **resize**：允许用户调整列的大小的行为。

- **visibility**：允许用户隐藏或显示列的行为。

## 创建行为

- **init()**：创建一个空的自定义行为，表示不进行任何自定义。

## 自定义列

- **tableColumnHeaders(_:)**：控制 `Table` 列标题视图的可见性。

- **TableColumnCustomization**：表示表中列的状态。

## 符合以下标准

- Equatable

- ExpressibleByArrayLiteral

- Sendable

- SendableMetatype

- SetAlgebra


---
source: https://developer.apple.com/documentation/SwiftUI/TableColumnCustomizationBehavior
crawled: 2025-12-02T17:39:58Z
---

# TableColumnCustomizationBehavior

**Structure**

A set of customization behaviors of a column that a table can offer to a user.

## Declaration

```swift
struct TableColumnCustomizationBehavior
```

## Overview

This is used as a value provided to [disabledCustomizationBehavior(_:)](TableColumnContent/disabledCustomizationBehavior.zh-Hans.md).

Setting any of these values as the `disabledCustomizationBehavior(_:)` doesn’t have any effect on iOS.

## Getting the customization behavior

- **all**: All customization behaviors.
- **reorder**: A behavior that allows the column to be reordered by the user.
- **resize**: A behavior that allows the column to be resized by the user.
- **visibility**: A behavior that allows the column to be hidden or revealed by the user.

## Creating a behavior

- **init()**: Creates an empty customization behavior, representing no customization

## Customizing columns

- **tableColumnHeaders(_:)**: Controls the visibility of a `Table`’s column header views.
- **TableColumnCustomization**: A representation of the state of the columns in a table.

## Conforms To

- Equatable
- ExpressibleByArrayLiteral
- Sendable
- SendableMetatype
- SetAlgebra

