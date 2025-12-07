--- 来源：https://developer.apple.com/documentation/SwiftUI/ScrollPosition/init(idType:x:)

抓取时间：2025-12-01T11:31:13Z

---

# init(idType:x:)

**Initializer**

创建一个新的滚动位置，滚动到指定的 y 值。

## 声明

```swift
init(idType: (some Hashable & Sendable).Type = Never.self, x: CGFloat)
```

## 讨论

您可以为滚动位置指定一个类型。此类型应与滚动目标布局中视图关联的 ID 类型匹配。滚动视图将查找这些视图，并使用该 ID 更新滚动位置的值。


---
source: https://developer.apple.com/documentation/SwiftUI/ScrollPosition/init(idType:x:)
crawled: 2025-12-01T11:31:13Z
---

# init(idType:x:)

**Initializer**

Creates a new scroll position to be scrolled to the provided y value.

## Declaration

```swift
init(idType: (some Hashable & Sendable).Type = Never.self, x: CGFloat)
```

## Discussion

You can provide a type to the scroll position. This type should match the type of IDs associated to views in a scroll target layout. The scroll view will look for those views to update the value of the scroll position with.

