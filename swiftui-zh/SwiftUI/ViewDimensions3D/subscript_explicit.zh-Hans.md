--- 来源：https://developer.apple.com/documentation/SwiftUI/ViewDimensions3D/subscript(explicit:)

抓取时间：2025-12-01T11:26:22Z

---

# subscript(explicit:)

**实例下标**

获取给定深度对齐参考线的显式值

## 声明

```swift
subscript(explicit guide: DepthAlignment) -> CGFloat? { get }
```

## 概述

使用参考线作为索引，从上下文中读取相应视图中特定参考线的深度偏移量：

```swift
.alignmentGuide(.front) { context in
    context[.front] - 10
}
```

如果参考线不存在值，则此下标返回 `nil`。

有关如何在 Swift 中使用下标访问集合、列表或序列的成员元素的信息，请参阅《Swift 程序设计语言》中的 [https://docs.swift.org/swift-book/LanguageGuide/Subscripts.html]。


---
source: https://developer.apple.com/documentation/SwiftUI/ViewDimensions3D/subscript(explicit:)
crawled: 2025-12-01T11:26:22Z
---

# subscript(explicit:)

**Instance Subscript**

Gets the explicit value of the given depth alignment guide

## Declaration

```swift
subscript(explicit guide: DepthAlignment) -> CGFloat? { get }
```

## Overview

Find the depth offset of a particular guide in the corresponding view by using that guide as an index to read from the context:

```swift
.alignmentGuide(.front) { context in
    context[.front] - 10
}
```

This subscript returns `nil` if no value exists for the guide.

For information about using subscripts in Swift to access member elements of a collection, list, or, sequence, see [https://docs.swift.org/swift-book/LanguageGuide/Subscripts.html] in *The Swift Programming Language*.

