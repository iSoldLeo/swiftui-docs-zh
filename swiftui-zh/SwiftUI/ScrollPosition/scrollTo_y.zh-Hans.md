--- 来源：https://developer.apple.com/documentation/SwiftUI/ScrollPosition/scrollTo(y:)

抓取时间：2025-12-03T06:42:07Z

---

# scrollTo(y:)

**实例方法**

将滚动视图滚动到您提供的 y 值。

## 声明

```swift
mutating func scrollTo(y: CGFloat)
```

## 讨论

滚动视图会根据其内容内边距选择 x 值，并将此值限制在滚动到其实际内容大小的范围内。


---
source: https://developer.apple.com/documentation/SwiftUI/ScrollPosition/scrollTo(y:)
crawled: 2025-12-03T06:42:07Z
---

# scrollTo(y:)

**Instance Method**

Scrolls the position of the scroll view to the y value you provide.

## Declaration

```swift
mutating func scrollTo(y: CGFloat)
```

## Discussion

The scroll view chooses the x value based on the content insets of the scroll view and will clamp this value to only scroll to the size of its actual content.

