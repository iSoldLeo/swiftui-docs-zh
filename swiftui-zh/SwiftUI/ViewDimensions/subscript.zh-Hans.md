---
来源： https://developer.apple.com/documentation/SwiftUI/ViewDimensions/subscript(_:)
抓取时间： 2025-12-01T11:26:17Z
---

# 下标(_:)

**实例下标**

获取给定水平向导的值。

## 声明

```swift
subscript(guide: HorizontalAlignment) -> CGFloat { get }
```

## 概览

通过将特定向导作为索引从上下文中读取，在相应视图中找到该向导的偏移量：

```swift
.alignmentGuide(.leading) { context in
    context[.leading] - 10
}
```

有关在 Swift 中使用下标访问集合、列表或序列的成员元素的信息，请参阅 *The Swift Programming Language* 中的 [https://docs.swift.org/swift-book/LanguageGuide/Subscripts.html]。

## 访问引导值

- **subscript(explicit:)**：获取给定水平对齐向导的显式值。


---
source: https://developer.apple.com/documentation/SwiftUI/ViewDimensions/subscript(_:)
crawled: 2025-12-01T11:26:17Z
---

# subscript(_:)

**Instance Subscript**

Gets the value of the given horizontal guide.

## Declaration

```swift
subscript(guide: HorizontalAlignment) -> CGFloat { get }
```

## Overview

Find the offset of a particular guide in the corresponding view by using that guide as an index to read from the context:

```swift
.alignmentGuide(.leading) { context in
    context[.leading] - 10
}
```

For information about using subscripts in Swift to access member elements of a collection, list, or, sequence, see [https://docs.swift.org/swift-book/LanguageGuide/Subscripts.html] in *The Swift Programming Language*.

## Accessing guide values

- **subscript(explicit:)**: Gets the explicit value of the given horizontal alignment guide.

