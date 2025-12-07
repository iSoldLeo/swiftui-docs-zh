--- 来源：https://developer.apple.com/documentation/SwiftUI/NavigationSplitViewStyle/automatic

抓取时间：2025-12-03T06:11:15Z

---

# automatic

**类型属性**

一种导航分割样式，可根据当前上下文自动解析其外观。

## 声明

```swift
@MainActor @preconcurrency static var automatic: AutomaticNavigationSplitViewStyle { get }
```

## 创建内置样式

- **balanced**：一种导航分割样式，可在显示前导列时缩小详情内容的大小，以便腾出空间。

- **prominentDetail**：一种导航分割样式，可在隐藏或显示前导列时尝试保持详情内容的大小不变。


---
source: https://developer.apple.com/documentation/SwiftUI/NavigationSplitViewStyle/automatic
crawled: 2025-12-03T06:11:15Z
---

# automatic

**Type Property**

A navigation split style that resolves its appearance automatically based on the current context.

## Declaration

```swift
@MainActor @preconcurrency static var automatic: AutomaticNavigationSplitViewStyle { get }
```

## Creating built-in styles

- **balanced**: A navigation split style that reduces the size of the detail content to make room when showing the leading column or columns.
- **prominentDetail**: A navigation split style that attempts to maintain the size of the detail content when hiding or showing the leading columns.

