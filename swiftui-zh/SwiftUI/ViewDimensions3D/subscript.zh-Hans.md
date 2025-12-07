--- 来源：https://developer.apple.com/documentation/SwiftUI/ViewDimensions3D/subscript(_:)

抓取时间：2025-12-03T06:37:09Z

---

# subscript(_:)

**实例下标**

获取给定深度参考线的值。

## 声明

```swift
subscript(guide: DepthAlignment) -> CGFloat { get }
```

## 概述

通过将该参考线作为索引从上下文中读取，找到对应视图中特定参考线的偏移量：

```swift
.alignmentGuide(.front) { context in
    context[.front] - 10
}
```

有关在 Swift 中使用下标访问集合、列表或序列成员元素的更多信息，请参阅《Swift 程序设计语言》中的 [https://docs.swift.org/swift-book/LanguageGuide/Subscripts.html]。


---
source: https://developer.apple.com/documentation/SwiftUI/ViewDimensions3D/subscript(_:)
crawled: 2025-12-03T06:37:09Z
---

# subscript(_:)

**Instance Subscript**

Gets the value of the given depth guide.

## Declaration

```swift
subscript(guide: DepthAlignment) -> CGFloat { get }
```

## Overview

Find the offset of a particular guide in the corresponding view by using that guide as an index to read from the context:

```swift
.alignmentGuide(.front) { context in
    context[.front] - 10
}
```

For information about using subscripts in Swift to access member elements of a collection, list, or, sequence, see [https://docs.swift.org/swift-book/LanguageGuide/Subscripts.html] in *The Swift Programming Language*.

