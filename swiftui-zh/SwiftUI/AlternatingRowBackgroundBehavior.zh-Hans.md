--- 来源：https://developer.apple.com/documentation/SwiftUI/AlternatingRowBackgroundBehavior
抓取时间：2025-12-02T17:39:39Z

---

# AlternatingRowBackgroundBehavior

**Structure**

用于设置视图的交替行背景样式。

## 声明

```swift
struct AlternatingRowBackgroundBehavior
```

## 概述

使用此类型的值时，请添加 [alternatingRowBackgrounds(_:)](View/alternatingRowBackgrounds.zh-Hans.md) 修饰符。

## 获取交替行背景行为

- **automatic**：自动启用交替行背景行为。

- **enabled**：将为适用的视图启用交替行。

- **disabled**：对于适用的视图，将禁用交替行显示。

## 配置背景

- **listRowBackground(_:)**：在列表行项后放置自定义背景视图。

- **alternatingRowBackgrounds(_:)**：覆盖此视图中的列表和表格是否具有交替行背景。

- **backgroundProminence**：与此环境关联的视图下方背景的突出显示程度。

- **BackgroundProminence**：其他视图下方背景的突出显示程度。

## 符合以下标准

- Equatable

- Hashable

- Sendable

- SendableMetatype


---
source: https://developer.apple.com/documentation/SwiftUI/AlternatingRowBackgroundBehavior
crawled: 2025-12-02T17:39:39Z
---

# AlternatingRowBackgroundBehavior

**Structure**

The styling of views with respect to alternating row backgrounds.

## Declaration

```swift
struct AlternatingRowBackgroundBehavior
```

## Overview

Use values of this type with the [alternatingRowBackgrounds(_:)](View/alternatingRowBackgrounds.zh-Hans.md) modifier.

## Getting alternating row background behavior

- **automatic**: The automatic alternating row background behavior.
- **enabled**: Alternating rows will be enabled for applicable views.
- **disabled**: Alternating rows will be disabled for applicable views.

## Configuring backgrounds

- **listRowBackground(_:)**: Places a custom background view behind a list row item.
- **alternatingRowBackgrounds(_:)**: Overrides whether lists and tables in this view have alternating row backgrounds.
- **backgroundProminence**: The prominence of the background underneath views associated with this environment.
- **BackgroundProminence**: The prominence of backgrounds underneath other views.

## Conforms To

- Equatable
- Hashable
- Sendable
- SendableMetatype

