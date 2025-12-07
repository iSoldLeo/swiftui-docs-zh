---
来源：https://developer.apple.com/documentation/SwiftUI/ViewDimensions/subscript(explicit:)
抓取时间： 2025-12-03T06:37:06Z
---

# subscript(explicit:)

**实例下标**

获取给定水平对齐方式的显式值。

## 声明

```swift
subscript(explicit guide: HorizontalAlignment) -> CGFloat? { get }
```

## 概览

将特定导轨作为索引从上下文中读取，从而在相应视图中找到该导轨的水平偏移量：

```swift
.alignmentGuide(.leading) { context in
    context[.leading] - 10
}
```

如果不存在该向导的值，该下标将返回 `nil`。

有关在 Swift 中使用下标访问集合、列表或序列的成员元素的信息，请参阅 *The Swift Programming Language* 中的 [https://docs.swift.org/swift-book/LanguageGuide/Subscripts.html]。

## 访问引导值

- **subscript(_:)**：获取给定水平向导的值。


---
source: https://developer.apple.com/documentation/SwiftUI/ViewDimensions/subscript(explicit:)
crawled: 2025-12-03T06:37:06Z
---

# subscript(explicit:)

**Instance Subscript**

Gets the explicit value of the given horizontal alignment guide.

## Declaration

```swift
subscript(explicit guide: HorizontalAlignment) -> CGFloat? { get }
```

## Overview

Find the horizontal offset of a particular guide in the corresponding view by using that guide as an index to read from the context:

```swift
.alignmentGuide(.leading) { context in
    context[.leading] - 10
}
```

This subscript returns `nil` if no value exists for the guide.

For information about using subscripts in Swift to access member elements of a collection, list, or, sequence, see [https://docs.swift.org/swift-book/LanguageGuide/Subscripts.html] in *The Swift Programming Language*.

## Accessing guide values

- **subscript(_:)**: Gets the value of the given horizontal guide.

