---
来源：https://developer.apple.com/documentation/SwiftUI/Shape/symmetricDifference(_:eoFill:)
抓取时间： 2025-12-01T02:33:01Z
---

# symmetricDifference(_:eoFill:)

**实例方法**

返回一个新形状，其填充区域要么来自此形状，要么来自给定形状，但不能同时来自两个形状。

### 声明

```swift
nonisolated func symmetricDifference<T>(_ other: T, eoFill: Bool = false) -> some Shape where T : Shape

```

## 参数

- **other**：要差分的形状。
- **eoFill**：是使用偶数规则（如果为 true），还是使用非零规则（如果为 false）来确定将哪些区域作为形状的内部区域。

## 返回值

一个新形状。

## 讨论

生成的形状的填充区域是包含在此形状或`other`中的填充区域，而不是两者都包含。

任一形状中任何未封闭的子路径都被假定为封闭的。使用偶数填充规则或非零填充规则填充此形状的结果是相同的。

## 对形状执行操作

- **intersection(_:eoFill:)**：返回一个新形状，其填充区域与两个形状相同。
- **lineIntersection(_:eoFill:)**：返回一个新形状，该形状的一条直线与给定形状的填充区域重叠。
- **lineSubtraction(_:eoFill:)**：返回一个新形状，该形状的直线不会与给定形状的填充区域重叠。
- **subtracting(_:eoFill:)**：返回一个新形状，该形状的填充区域不在给定形状中。
- **union(_:eoFill:)**：返回一个新形状，其中包含此形状或给定形状中的填充区域。


---
source: https://developer.apple.com/documentation/SwiftUI/Shape/symmetricDifference(_:eoFill:)
crawled: 2025-12-01T02:33:01Z
---

# symmetricDifference(_:eoFill:)

**Instance Method**

Returns a new shape with filled regions either from this shape or the given shape, but not in both.

## Declaration

```swift
nonisolated func symmetricDifference<T>(_ other: T, eoFill: Bool = false) -> some Shape where T : Shape

```

## Parameters

- **other**: The shape to difference.
- **eoFill**: Whether to use the even-odd rule for determining which areas to treat as the interior of the shapes (if true), or the non-zero rule (if false).

## Return Value

A new shape.

## Discussion

The filled region of the resulting shape is the filled region contained in either this shape or `other`, but not both.

Any unclosed subpaths in either shape are assumed to be closed. The result of filling this shape using either even-odd or non-zero fill rules is identical.

## Performing operations on a shape

- **intersection(_:eoFill:)**: Returns a new shape with filled regions common to both shapes.
- **lineIntersection(_:eoFill:)**: Returns a new shape with a line from this shape that overlaps the filled regions of the given shape.
- **lineSubtraction(_:eoFill:)**: Returns a new shape with a line from this shape that does not overlap the filled region of the given shape.
- **subtracting(_:eoFill:)**: Returns a new shape with filled regions from this shape that are not in the given shape.
- **union(_:eoFill:)**: Returns a new shape with filled regions in either this shape or the given shape.

