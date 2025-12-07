--- 来源：https://developer.apple.com/documentation/SwiftUI/PresentationBackgroundInteraction/enabled

抓取时间：2025-12-03T06:02:37Z

---

# enabled

**类型属性**

用户可以与演示文稿背后的视图进行交互。

## 声明

```swift
static var enabled: PresentationBackgroundInteraction { get }
```

## 获取交互类型

- **automatic**：演示文稿的默认后台交互。

- **disabled**：用户无法与演示文稿背后的视图进行交互。

- **enabled(upThrough:)**：用户可以与演示文稿背后的视图进行交互，但交互深度需达到指定值。


---
source: https://developer.apple.com/documentation/SwiftUI/PresentationBackgroundInteraction/enabled
crawled: 2025-12-03T06:02:37Z
---

# enabled

**Type Property**

People can interact with the view behind a presentation.

## Declaration

```swift
static var enabled: PresentationBackgroundInteraction { get }
```

## Getting interaction types

- **automatic**: The default background interaction for the presentation.
- **disabled**: People can’t interact with the view behind a presentation.
- **enabled(upThrough:)**: People can interact with the view behind a presentation up through a specified detent.

