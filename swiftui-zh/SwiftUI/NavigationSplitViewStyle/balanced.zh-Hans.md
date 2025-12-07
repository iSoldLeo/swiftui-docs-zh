--- 来源：https://developer.apple.com/documentation/SwiftUI/NavigationSplitViewStyle/balanced

抓取时间：2025-12-03T06:11:16Z

---

#balanced

**类型属性**

一种导航分割样式，用于在显示前导列时缩小详情内容的大小，以便腾出空间。

## 声明

```swift
@MainActor @preconcurrency static var balanced: BalancedNavigationSplitViewStyle { get }
```

## 创建内置样式

- **automatic**：一种导航分割样式，可根据当前上下文自动解析其外观。

- **prominentDetail**：一种导航分割样式，在隐藏或显示前导列时，尝试保持详情内容的大小不变。


---
source: https://developer.apple.com/documentation/SwiftUI/NavigationSplitViewStyle/balanced
crawled: 2025-12-03T06:11:16Z
---

# balanced

**Type Property**

A navigation split style that reduces the size of the detail content to make room when showing the leading column or columns.

## Declaration

```swift
@MainActor @preconcurrency static var balanced: BalancedNavigationSplitViewStyle { get }
```

## Creating built-in styles

- **automatic**: A navigation split style that resolves its appearance automatically based on the current context.
- **prominentDetail**: A navigation split style that attempts to maintain the size of the detail content when hiding or showing the leading columns.

