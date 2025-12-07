--- 来源：https://developer.apple.com/documentation/SwiftUI/PresentationBackgroundInteraction/disabled

抓取时间：2025-12-03T06:02:36Z

---

# 已禁用

**类型属性**

用户无法与演示文稿背后的视图进行交互。

## 声明

```swift
static var disabled: PresentationBackgroundInteraction { get }
```

## 获取交互类型

- **automatic**：演示文稿的默认背景交互。

- **enabled**：用户可以与演示文稿背后的视图进行交互。

- **enabled(upThrough:)**：用户可以与演示文稿背后的视图进行交互，但交互范围会受到一定限制。


---
source: https://developer.apple.com/documentation/SwiftUI/PresentationBackgroundInteraction/disabled
crawled: 2025-12-03T06:02:36Z
---

# disabled

**Type Property**

People can’t interact with the view behind a presentation.

## Declaration

```swift
static var disabled: PresentationBackgroundInteraction { get }
```

## Getting interaction types

- **automatic**: The default background interaction for the presentation.
- **enabled**: People can interact with the view behind a presentation.
- **enabled(upThrough:)**: People can interact with the view behind a presentation up through a specified detent.

