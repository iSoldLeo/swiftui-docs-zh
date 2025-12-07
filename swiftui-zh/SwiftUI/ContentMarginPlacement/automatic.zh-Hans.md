--- 来源：https://developer.apple.com/documentation/SwiftUI/ContentMarginPlacement/automatic
抓取时间：2025-12-03T06:37:11Z

---

# automatic

**类型属性**

自动放置。

## 声明

```swift
static var automatic: ContentMarginPlacement { get }
```

## 讨论

支持自定义边距的视图可以使用此放置方式自动应用边距。例如，[ScrollView](../ScrollView.zh-Hans.md) 将使用此放置方式自动将内容和滚动指示器内缩指定量。

## 获取放置方式

- **scrollContent**：滚动内容放置方式。

- **scrollIndicators**：滚动指示器放置方式。


---
source: https://developer.apple.com/documentation/SwiftUI/ContentMarginPlacement/automatic
crawled: 2025-12-03T06:37:11Z
---

# automatic

**Type Property**

The automatic placement.

## Declaration

```swift
static var automatic: ContentMarginPlacement { get }
```

## Discussion

Views that support margin customization can automatically use margins with this placement. For example, a [ScrollView](../ScrollView.zh-Hans.md) will use this placement to automatically inset both its content and scroll indicators by the specified amount.

## Getting the placement

- **scrollContent**: The scroll content placement.
- **scrollIndicators**: The scroll indicators placement.

