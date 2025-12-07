--- 来源：https://developer.apple.com/documentation/SwiftUI/ContentMarginPlacement
抓取时间：2025-12-02T17:38:56Z

---

# ContentMarginPlacement

**Structure**

边距的放置位置。

## 声明

```swift
struct ContentMarginPlacement
```

## 概述

不同的视图可以支持自定义显示在该视图不同部分的边距。使用此类型的值可以自定义特定放置位置的边距。

例如，使用 [scrollIndicators](ContentMarginPlacement/scrollIndicators.zh-Hans.md) 放置位置可以分别自定义可滚动视图的滚动指示器的边距和可滚动视图内容的边距。

将此类型与 [contentMargins(_:for:)](View/contentMargins___for.zh-Hans.md) 修饰符一起使用。

## 获取位置

- **automatic**：自动位置。

- **scrollContent**：滚动内容位置。

- **scrollIndicators**：滚动指示器位置。

## 设置边距

- **contentMargins(_:for:)**：配置指定位置的内容边距。

- **contentMargins(_:_:for:)**：配置指定位置的内容边距。


---
source: https://developer.apple.com/documentation/SwiftUI/ContentMarginPlacement
crawled: 2025-12-02T17:38:56Z
---

# ContentMarginPlacement

**Structure**

The placement of margins.

## Declaration

```swift
struct ContentMarginPlacement
```

## Overview

Different views can support customizating margins that appear in different parts of that view. Use values of this type to customize those margins of a particular placement.

For example, use a [scrollIndicators](ContentMarginPlacement/scrollIndicators.zh-Hans.md) placement to customize the margins of scrollable view’s scroll indicators separately from the margins of a scrollable view’s content.

Use this type with the [contentMargins(_:for:)](View/contentMargins___for.zh-Hans.md) modifier.

## Getting the placement

- **automatic**: The automatic placement.
- **scrollContent**: The scroll content placement.
- **scrollIndicators**: The scroll indicators placement.

## Setting margins

- **contentMargins(_:for:)**: Configures the content margin for a provided placement.
- **contentMargins(_:_:for:)**: Configures the content margin for a provided placement.

