---
来源： https://developer.apple.com/documentation/SwiftUI/ContentMode/fill
抓取时间： 2025-12-03T06:27:38Z
---

# ContentMode.fill

**Case**

该选项可调整内容大小，使其占据垂直和水平方向的所有可用空间。

## 声明

```swift
case fill
```

## 讨论

该模式保留内容的宽高比。如果内容的宽高比与可用空间不一致，则内容在一个轴上的大小会与可用空间相同，而在另一个轴上则会变大。

## 获取内容模式

- **ContentMode.fit**：该选项可调整内容大小，使其在垂直和水平方向上都在可用空间内。


---
source: https://developer.apple.com/documentation/SwiftUI/ContentMode/fill
crawled: 2025-12-03T06:27:38Z
---

# ContentMode.fill

**Case**

An option that resizes the content so it occupies all available space, both vertically and horizontally.

## Declaration

```swift
case fill
```

## Discussion

This mode preserves the content’s aspect ratio. If the content doesn’t have the same aspect ratio as the available space, the content becomes the same size as the available space on one axis, and larger on the other axis.

## Getting content modes

- **ContentMode.fit**: An option that resizes the content so it’s all within the available space, both vertically and horizontally.

