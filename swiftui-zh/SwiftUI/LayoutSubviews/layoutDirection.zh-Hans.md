---
来源： https://developer.apple.com/documentation/SwiftUI/LayoutSubviews/layoutDirection
抓取时间： 2025-12-02T20:59:13Z
---

# 布局方向

**实例属性**

容器视图继承的布局方向。

## 声明

```swift
var layoutDirection: LayoutDirection
```

## 讨论

SwiftUI 支持从左到右和从右到左两种方向。在自定义布局容器中读取此属性，可以了解容器所处的环境。

在大多数情况下，您不需要根据此值采取任何操作。当模式切换时，SwiftUI 会水平翻转每个视图在其父视图中的 x 位置，因此布局计算会自动为两个方向产生所需的效果。


---
source: https://developer.apple.com/documentation/SwiftUI/LayoutSubviews/layoutDirection
crawled: 2025-12-02T20:59:13Z
---

# layoutDirection

**Instance Property**

The layout direction inherited by the container view.

## Declaration

```swift
var layoutDirection: LayoutDirection
```

## Discussion

SwiftUI supports both left-to-right and right-to-left directions. Read this property within a custom layout container to find out which environment the container is in.

In most cases, you don’t need to take any action based on this value. SwiftUI horizontally flips the x position of each view within its parent when the mode switches, so layout calculations automatically produce the desired effect for both directions.

