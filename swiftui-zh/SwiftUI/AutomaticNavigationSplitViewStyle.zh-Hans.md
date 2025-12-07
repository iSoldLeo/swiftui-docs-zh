---
来源： https://developer.apple.com/documentation/SwiftUI/AutomaticNavigationSplitViewStyle
抓取时间： 2025-12-03T06:11:19Z
---

# AutomaticNavigationSplitViewStyle

**Structure**

根据当前上下文自动调整外观的导航分割样式。

### 声明

```swift
@MainActor @preconcurrency struct AutomaticNavigationSplitViewStyle
```

## 概览

使用 [automatic](NavigationSplitViewStyle/automatic.zh-Hans.md) 构建此样式。

## 创建导航分割视图样式

- **init()**：创建自动导航分割视图样式的实例。

## 支持类型

- **BalancedNavigationSplitViewStyle**：一种导航拆分样式，可缩小详细内容的大小，以便在显示前导列时腾出空间。
- **ProminentDetailNavigationSplitViewStyle**：一种导航分割样式，在隐藏或显示前导列时尝试保持详细内容的大小。
- **NavigationSplitViewStyleConfiguration**：导航分割视图实例的属性。

## 符合

- 导航分割视图样式


---
source: https://developer.apple.com/documentation/SwiftUI/AutomaticNavigationSplitViewStyle
crawled: 2025-12-03T06:11:19Z
---

# AutomaticNavigationSplitViewStyle

**Structure**

A navigation split style that resolves its appearance automatically based on the current context.

## Declaration

```swift
@MainActor @preconcurrency struct AutomaticNavigationSplitViewStyle
```

## Overview

Use [automatic](NavigationSplitViewStyle/automatic.zh-Hans.md) to construct this style.

## Creating the navigation split view style

- **init()**: Creates an instance of the automatic navigation split view style.

## Supporting types

- **BalancedNavigationSplitViewStyle**: A navigation split style that reduces the size of the detail content to make room when showing the leading column or columns.
- **ProminentDetailNavigationSplitViewStyle**: A navigation split style that attempts to maintain the size of the detail content when hiding or showing the leading columns.
- **NavigationSplitViewStyleConfiguration**: The properties of a navigation split view instance.

## Conforms To

- NavigationSplitViewStyle

