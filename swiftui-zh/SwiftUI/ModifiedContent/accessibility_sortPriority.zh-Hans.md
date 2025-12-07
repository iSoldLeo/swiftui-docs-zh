---
来源：https://developer.apple.com/documentation/SwiftUI/ModifiedContent/accessibility(sortPriority:)
抓取时间： 2025-11-30T21:31:38Z
---

# accessibility(sortPriority:)

**实例方法**

设置该视图的辅助功能元素相对于同级其他元素的排序优先顺序。

## 声明

```swift
nonisolated func accessibility(sortPriority: Double) -> ModifiedContent<Content, Modifier>
```

## 讨论

数字越大，排序越靠前。默认排序优先级为 0。


---
source: https://developer.apple.com/documentation/SwiftUI/ModifiedContent/accessibility(sortPriority:)
crawled: 2025-11-30T21:31:38Z
---

# accessibility(sortPriority:)

**Instance Method**

Sets the sort priority order for this view’s accessibility element, relative to other elements at the same level.

## Declaration

```swift
nonisolated func accessibility(sortPriority: Double) -> ModifiedContent<Content, Modifier>
```

## Discussion

Higher numbers are sorted first. The default sort priority is zero.

