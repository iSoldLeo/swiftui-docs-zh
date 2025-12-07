--- 来源：https://developer.apple.com/documentation/SwiftUI/ScrollPosition/scrollTo(id:anchor:)

抓取时间：2025-12-03T06:42:04Z

---

# scrollTo(id:anchor:)

**实例方法**

将滚动视图滚动到具有指定标识值和锚点的视图。

## 声明

```swift
mutating func scrollTo(id: some Hashable & Sendable, anchor: UnitPoint? = nil)
```

## 说明

使用 `View/scrollTargetLayout()` 修饰符告知滚动视图应在哪个布局中查找具有指定标识值的视图。


---
source: https://developer.apple.com/documentation/SwiftUI/ScrollPosition/scrollTo(id:anchor:)
crawled: 2025-12-03T06:42:04Z
---

# scrollTo(id:anchor:)

**Instance Method**

Scrolls the position of the scroll view to a view with a identity value and anchor you provide.

## Declaration

```swift
mutating func scrollTo(id: some Hashable & Sendable, anchor: UnitPoint? = nil)
```

## Discussion

Inform the scroll view of which layout it should look for view’s with the identity value you provide using the `View/scrollTargetLayout()` modifier.

