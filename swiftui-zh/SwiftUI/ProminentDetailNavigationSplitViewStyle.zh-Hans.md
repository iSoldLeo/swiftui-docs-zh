---
来源： https://developer.apple.com/documentation/SwiftUI/ProminentDetailNavigationSplitViewStyle
抓取时间： 2025-12-03T06:11:21Z
---

# ProminentDetailNavigationSplitViewStyle

**Structure**

一种导航分割样式，在隐藏或显示前导列时，可保持详细内容的大小。

### 声明

```swift
@MainActor @preconcurrency struct ProminentDetailNavigationSplitViewStyle
```

## 概览

使用 [prominentDetail](NavigationSplitViewStyle/prominentDetail.zh-Hans.md) 构建此样式。

## 创建导航分割视图样式

- **init()**：创建[ProminentDetailNavigationSplitViewStyle](ProminentDetailNavigationSplitViewStyle.zh-Hans.md) 的实例。

## 支持类型

- **AutomaticNavigationSplitViewStyle**：根据当前上下文自动调整外观的导航分割样式。
- **BalancedNavigationSplitViewStyle**：一种导航拆分样式，在显示前导列时缩小详细内容的大小以腾出空间。
- **NavigationSplitViewStyleConfiguration**：导航分割视图实例的属性。

## 符合

- 导航分割视图样式


---
source: https://developer.apple.com/documentation/SwiftUI/ProminentDetailNavigationSplitViewStyle
crawled: 2025-12-03T06:11:21Z
---

# ProminentDetailNavigationSplitViewStyle

**Structure**

A navigation split style that attempts to maintain the size of the detail content when hiding or showing the leading columns.

## Declaration

```swift
@MainActor @preconcurrency struct ProminentDetailNavigationSplitViewStyle
```

## Overview

Use [prominentDetail](NavigationSplitViewStyle/prominentDetail.zh-Hans.md) to construct this style.

## Creating the navigation split view style

- **init()**: Creates an instance of [ProminentDetailNavigationSplitViewStyle](ProminentDetailNavigationSplitViewStyle.zh-Hans.md).

## Supporting types

- **AutomaticNavigationSplitViewStyle**: A navigation split style that resolves its appearance automatically based on the current context.
- **BalancedNavigationSplitViewStyle**: A navigation split style that reduces the size of the detail content to make room when showing the leading column or columns.
- **NavigationSplitViewStyleConfiguration**: The properties of a navigation split view instance.

## Conforms To

- NavigationSplitViewStyle

