--- 来源：https://developer.apple.com/documentation/SwiftUI/PresentationBackgroundInteraction/automatic

抓取时间：2025-12-03T06:02:35Z

---

# automatic

**Type 属性**

演示文稿的默认后台交互方式。

## 声明

```swift
static var automatic: PresentationBackgroundInteraction { get }
```

## 获取交互类型

- **disabled**：用户无法与演示文稿背后的视图进行交互。

- **enabled**：用户可以与演示文稿背后的视图进行交互。

- **enabled(upThrough:)**：用户可以与演示文稿背后的视图进行交互，但交互深度需达到指定值。


---
source: https://developer.apple.com/documentation/SwiftUI/PresentationBackgroundInteraction/automatic
crawled: 2025-12-03T06:02:35Z
---

# automatic

**Type Property**

The default background interaction for the presentation.

## Declaration

```swift
static var automatic: PresentationBackgroundInteraction { get }
```

## Getting interaction types

- **disabled**: People can’t interact with the view behind a presentation.
- **enabled**: People can interact with the view behind a presentation.
- **enabled(upThrough:)**: People can interact with the view behind a presentation up through a specified detent.

