---
来源： https://developer.apple.com/documentation/SwiftUI/ScrollGeometry/contentOffset
抓取时间： 2025-12-03T06:42:52Z
---

# contentOffset

**实例属性**

滚动视图的内容偏移量。

## 声明

```swift
var contentOffset: CGPoint { get set }
```

## 讨论

这是滚动视图在整体内容尺寸中的位置。当滚动视图的内容嵌套不为零或使用橡皮筋时，该值可能会在内容大小为零之前或超出内容大小。


---
source: https://developer.apple.com/documentation/SwiftUI/ScrollGeometry/contentOffset
crawled: 2025-12-03T06:42:52Z
---

# contentOffset

**Instance Property**

The content offset of the scroll view.

## Declaration

```swift
var contentOffset: CGPoint { get set }
```

## Discussion

This is the position of the scroll view within its overall content size. This value may extend before zero or beyond the content size when the content insets of the scroll view are non-zero or when rubber banding.

