--- 来源：https://developer.apple.com/documentation/SwiftUI/BalancedNavigationSplitViewStyle
抓取时间：2025-12-03T06:11:20Z

---

# BalancedNavigationSplitViewStyle

**Structure**

一种导航分割样式，它会缩小详情内容的大小，以便在显示前导列时腾出空间。

## 声明

```swift
@MainActor @preconcurrency struct BalancedNavigationSplitViewStyle
```

## 概述

使用 [balanced](NavigationSplitViewStyle/balanced.zh-Hans.md) 来构造此样式。

## 创建导航分割视图样式

- **init()**：创建 [BalancedNavigationSplitViewStyle](BalancedNavigationSplitViewStyle.zh-Hans.md) 的实例。

## 支持的类型

- **AutomaticNavigationSplitViewStyle**：一种导航拆分样式，可根据当前上下文自动解析其外观。

- **ProminentDetailNavigationSplitViewStyle**：一种导航拆分样式，在隐藏或显示前导列时，会尝试保持详细信息内容的大小不变。

- **NavigationSplitViewStyleConfiguration**：导航拆分视图实例的属性。

## 符合以下规范

- NavigationSplitViewStyle


---
source: https://developer.apple.com/documentation/SwiftUI/BalancedNavigationSplitViewStyle
crawled: 2025-12-03T06:11:20Z
---

# BalancedNavigationSplitViewStyle

**Structure**

A navigation split style that reduces the size of the detail content to make room when showing the leading column or columns.

## Declaration

```swift
@MainActor @preconcurrency struct BalancedNavigationSplitViewStyle
```

## Overview

Use [balanced](NavigationSplitViewStyle/balanced.zh-Hans.md) to construct this style.

## Creating the navigation split view style

- **init()**: Creates an instance of [BalancedNavigationSplitViewStyle](BalancedNavigationSplitViewStyle.zh-Hans.md).

## Supporting types

- **AutomaticNavigationSplitViewStyle**: A navigation split style that resolves its appearance automatically based on the current context.
- **ProminentDetailNavigationSplitViewStyle**: A navigation split style that attempts to maintain the size of the detail content when hiding or showing the leading columns.
- **NavigationSplitViewStyleConfiguration**: The properties of a navigation split view instance.

## Conforms To

- NavigationSplitViewStyle

