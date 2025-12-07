--- 来源：https://developer.apple.com/documentation/SwiftUI/ListItemTint
抓取时间：2025-12-02T17:39:32Z

---

# ListItemTint

**Structure**

可应用于列表内容的着色效果配置。

## 声明

```swift
struct ListItemTint
```

## 概述

将这些着色值之一与 [listItemTint(_:)](View/listItemTint.zh-Hans.md) 视图修饰符一起使用。包含列表会以平台特定的方式应用着色。

## 获取列表项着色选项

- **monochrome**：标准灰度着色效果。

- **fixed(_:)**：显式着色颜色。

- **preferred(_:)**：系统可以覆盖的显式色调颜色。

## 配置行

- **listItemTint(_:)**：为列表中的内容设置固定色调颜色。

## 符合以下标准

- Sendable

- SendableMetatype


---
source: https://developer.apple.com/documentation/SwiftUI/ListItemTint
crawled: 2025-12-02T17:39:32Z
---

# ListItemTint

**Structure**

A tint effect configuration that you can apply to content in a list.

## Declaration

```swift
struct ListItemTint
```

## Overview

Use one of these tint values with the [listItemTint(_:)](View/listItemTint.zh-Hans.md) view modifier. The containing list applies the tint in a platform-specific way.

## Getting list item tint options

- **monochrome**: A standard grayscale tint effect.
- **fixed(_:)**: An explicit tint color.
- **preferred(_:)**: An explicit tint color that the system can override.

## Configuring rows

- **listItemTint(_:)**: Sets a fixed tint color for content in a list.

## Conforms To

- Sendable
- SendableMetatype

