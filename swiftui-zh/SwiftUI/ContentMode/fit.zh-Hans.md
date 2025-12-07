---
来源： https://developer.apple.com/documentation/SwiftUI/ContentMode/fit
抓取时间： 2025-12-03T06:27:38Z
---

# ContentMode.fit

**Case**

该选项可调整内容大小，使其在垂直和水平方向上都处于可用空间内。

## 声明

```swift
case fit
```

## 讨论

该模式保留内容的宽高比。如果内容的纵横比与可用空间的纵横比不一致，则内容会在一个轴上变成与可用空间相同的大小，而在另一个轴上留下空白。

## 获取内容模式

- **ContentMode.fill**：该选项可调整内容大小，使其占据垂直和水平方向的所有可用空间。


---
source: https://developer.apple.com/documentation/SwiftUI/ContentMode/fit
crawled: 2025-12-03T06:27:38Z
---

# ContentMode.fit

**Case**

An option that resizes the content so it’s all within the available space, both vertically and horizontally.

## Declaration

```swift
case fit
```

## Discussion

This mode preserves the content’s aspect ratio. If the content doesn’t have the same aspect ratio as the available space, the content becomes the same size as the available space on one axis and leaves empty space on the other.

## Getting content modes

- **ContentMode.fill**: An option that resizes the content so it occupies all available space, both vertically and horizontally.

