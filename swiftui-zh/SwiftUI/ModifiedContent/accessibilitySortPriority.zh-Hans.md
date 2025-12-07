---
来源： https://developer.apple.com/documentation/SwiftUI/ModifiedContent/accessibilitySortPriority(_:)
抓取时间： 2025-11-30T21:32:02Z
---

# accessibilitySortPriority(_:)

**实例方法**

设置该视图的辅助功能元素相对于其他同级元素的排序优先顺序。

## 声明

```swift
nonisolated func accessibilitySortPriority(_ sortPriority: Double) -> ModifiedContent<Content, Modifier>
```

## 讨论

数字越大，排序越靠前。默认排序优先级为 0。


---
source: https://developer.apple.com/documentation/SwiftUI/ModifiedContent/accessibilitySortPriority(_:)
crawled: 2025-11-30T21:32:02Z
---

# accessibilitySortPriority(_:)

**Instance Method**

Sets the sort priority order for this view’s accessibility element, relative to other elements at the same level.

## Declaration

```swift
nonisolated func accessibilitySortPriority(_ sortPriority: Double) -> ModifiedContent<Content, Modifier>
```

## Discussion

Higher numbers are sorted first. The default sort priority is zero.

