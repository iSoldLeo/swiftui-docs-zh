---
来源：https://developer.apple.com/documentation/SwiftUI/Shape/subtracting(_:eoFill:)
抓取时间： 2025-12-01T02:33:01Z
---

# subtracting(_:eoFill:)

**实例方法**

返回一个新形状，其中包含此形状中未填充到给定形状中的填充区域。

## 声明

```swift
nonisolated func subtracting<T>(_ other: T, eoFill: Bool = false) -> some Shape where T : Shape

```

## 参数

- **other**：要减去的形状。
- **eoFill**：是否使用偶数规则（如果为 true）或非零规则（如果为 false）来决定将哪些区域作为形状的内部区域。

## 返回值

一个新形状。

## 讨论

生成的形状的填充区域是去掉填充区域`other`后的该形状的填充区域。

任一形状中任何未封闭的子路径都被假定为封闭的。使用偶数填充规则或非零填充规则填充该形状的结果是相同的。

## 对形状执行操作

- **intersection(_:eoFill:)**：返回一个新形状，其填充区域与两个形状相同。
- **lineIntersection(_:eoFill:)**：返回一个新形状，该形状的一条直线与给定形状的填充区域重叠。
- **lineSubtraction(_:eoFill:)**：返回一个新形状，该形状的直线不会与给定形状的填充区域重叠。
- **symmetricDifference(_:eoFill:)**：返回一个新形状，其填充区域要么来自此形状，要么来自给定形状，但不能同时来自两个形状。
- **union(_:eoFill:)**：返回一个新形状，该形状或给定形状中都有填充区域。


---
source: https://developer.apple.com/documentation/SwiftUI/Shape/subtracting(_:eoFill:)
crawled: 2025-12-01T02:33:01Z
---

# subtracting(_:eoFill:)

**Instance Method**

Returns a new shape with filled regions from this shape that are not in the given shape.

## Declaration

```swift
nonisolated func subtracting<T>(_ other: T, eoFill: Bool = false) -> some Shape where T : Shape

```

## Parameters

- **other**: The shape to subtract.
- **eoFill**: Whether to use the even-odd rule for determining which areas to treat as the interior of the shapes (if true), or the non-zero rule (if false).

## Return Value

A new shape.

## Discussion

The filled region of the resulting shape is the filled region of this shape with the filled region `other` removed from it.

Any unclosed subpaths in either shape are assumed to be closed. The result of filling this shape using either even-odd or non-zero fill rules is identical.

## Performing operations on a shape

- **intersection(_:eoFill:)**: Returns a new shape with filled regions common to both shapes.
- **lineIntersection(_:eoFill:)**: Returns a new shape with a line from this shape that overlaps the filled regions of the given shape.
- **lineSubtraction(_:eoFill:)**: Returns a new shape with a line from this shape that does not overlap the filled region of the given shape.
- **symmetricDifference(_:eoFill:)**: Returns a new shape with filled regions either from this shape or the given shape, but not in both.
- **union(_:eoFill:)**: Returns a new shape with filled regions in either this shape or the given shape.

