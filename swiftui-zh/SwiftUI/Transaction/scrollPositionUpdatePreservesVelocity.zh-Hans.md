---
来源： https://developer.apple.com/documentation/SwiftUI/Transaction/scrollPositionUpdatePreservesVelocity
抓取时间： 2025-12-03T06:17:27Z
---

# scrollPositionUpdatePreservesVelocity

**实例属性**

以编程方式更新滚动视图的滚动位置时，是否保留滚动视图任何活动滚动的当前速度。

## 声明

```swift
var scrollPositionUpdatePreservesVelocity: Bool { get set }
```

## 讨论

默认情况下，当滚动视图看到程序对其滚动位置进行更新时，它会停止任何活动滚动，以便进行一致的滚动。如果程序更新为动画，该属性将被忽略。


---
source: https://developer.apple.com/documentation/SwiftUI/Transaction/scrollPositionUpdatePreservesVelocity
crawled: 2025-12-03T06:17:27Z
---

# scrollPositionUpdatePreservesVelocity

**Instance Property**

Whether a programmatic update to the scroll position of a scroll view preserves the current velocity of any active scroll of the scroll view.

## Declaration

```swift
var scrollPositionUpdatePreservesVelocity: Bool { get set }
```

## Discussion

By default, when a scroll view sees a programmatic update to its scroll position, it will stop any active scrolls for unanimated scrolls. If a programmatic update is animated, this property is ignored.

