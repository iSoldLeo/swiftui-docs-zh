--- 来源：https://developer.apple.com/documentation/SwiftUI/ScrollPosition/init(idType:edge:)

抓取时间：2025-12-01T11:31:11Z

---

# init(idType:edge:)

**Initializer**

创建一个新的滚动位置，滚动到指定的边缘。

## 声明

```swift
init(idType: (some Hashable & Sendable).Type = Never.self, edge: Edge)
```

## 讨论

您可以提供一个类型来指定滚动视图应在其滚动目标布局中查找具有该类型 ID 的视图。


---
source: https://developer.apple.com/documentation/SwiftUI/ScrollPosition/init(idType:edge:)
crawled: 2025-12-01T11:31:11Z
---

# init(idType:edge:)

**Initializer**

Creates a new scroll position to be scrolled to the provided edge.

## Declaration

```swift
init(idType: (some Hashable & Sendable).Type = Never.self, edge: Edge)
```

## Discussion

You can provide a type to indicate the type of ID the scroll view should look for views with an ID of that type within its scroll target layout.

