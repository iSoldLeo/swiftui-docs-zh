---
来源： https://developer.apple.com/documentation/SwiftUI/Transaction/scrollContentOffsetAdjustmentBehavior
抓取时间： 2025-12-03T06:17:26Z
---

# scrollContentOffsetAdjustmentBehavior

**实例属性**

滚动视图对当前事务的内容偏移调整行为。

## 声明

```swift
var scrollContentOffsetAdjustmentBehavior: ScrollContentOffsetAdjustmentBehavior { get set }
```

## 讨论

滚动视图可根据当前上下文自动调整内容偏移。可以调整绝对偏移量，使内容保持在相对相同的位置。例如，当滚动到底部时，当滚动视图内容的整体大小发生变化时，滚动视图可保持底边滚动到底部。

在需要时，可使用此属性禁用此类调整。


---
source: https://developer.apple.com/documentation/SwiftUI/Transaction/scrollContentOffsetAdjustmentBehavior
crawled: 2025-12-03T06:17:26Z
---

# scrollContentOffsetAdjustmentBehavior

**Instance Property**

The behavior a scroll view will have regarding content offset adjustments for the current transaction.

## Declaration

```swift
var scrollContentOffsetAdjustmentBehavior: ScrollContentOffsetAdjustmentBehavior { get set }
```

## Discussion

A scroll view may automatically adjust its content offset based on the current context. The absolute offset may be adjusted to keep content in relatively the same place. For example, when scrolled to the bottom, a scroll view may keep the bottom edge scrolled to the bottom when the overall size of its content changes.

Use this property to disable these kinds of adjustments when needed.

