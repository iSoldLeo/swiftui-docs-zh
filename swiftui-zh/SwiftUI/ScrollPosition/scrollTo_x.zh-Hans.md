--- 来源：https://developer.apple.com/documentation/SwiftUI/ScrollPosition/scrollTo(x:)

抓取时间：2025-12-03T06:42:06Z

---

# scrollTo(x:)

**实例方法**

将滚动视图滚动到您提供的 x 值。

## 声明

```swift
mutating func scrollTo(x: CGFloat)
```

## 讨论

滚动视图会根据其内容内边距选择 y 值，并将该值限制在实际内容的大小范围内。


---
source: https://developer.apple.com/documentation/SwiftUI/ScrollPosition/scrollTo(x:)
crawled: 2025-12-03T06:42:06Z
---

# scrollTo(x:)

**Instance Method**

Scrolls the position of the scroll view to the x value you provide.

## Declaration

```swift
mutating func scrollTo(x: CGFloat)
```

## Discussion

The scroll view chooses the y value based on the content insets of the scroll view and will clamp this value to only scroll to the size of its actual content.

