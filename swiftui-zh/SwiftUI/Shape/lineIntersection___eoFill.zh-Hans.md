---
来源：https://developer.apple.com/documentation/SwiftUI/Shape/lineIntersection(_:eoFill:)
抓取时间： 2025-12-01T02:32:59Z
---

# lineIntersection(_:eoFill:)

**实例方法**

返回一个新形状，该形状的线条与给定形状的填充区域重叠。

## 声明

```swift
nonisolated func lineIntersection<T>(_ other: T, eoFill: Bool = false) -> some Shape where T : Shape

```

## 参数

- **other**：要相交的形状。
- **eoFill**：是否使用偶数规则（如果为 true）或非零规则（如果为 false）来确定将哪些区域视为形状的内部区域。

## 返回值

一个新形状。

## 讨论

生成的形状的线就是与`other`的填充区域重叠的线。

被剪切的相交子路径会产生开放子路径。未与`other` 相交的封闭子路径保持封闭。

## 对形状进行操作

- **intersection(_:eoFill:)**：返回一个新形状，其填充区域与两个形状相同。
- **lineSubtraction(_:eoFill:)**：返回一个新形状，该形状的一条直线不会与给定形状的填充区域重叠。
- **subtracting(_:eoFill:)**：返回一个新形状，该形状的填充区域不在给定形状中。
- **symmetricDifference(_:eoFill:)**：返回一个新形状，其填充区域要么来自此形状，要么来自给定形状，但不会同时来自这两个形状。
- **union(_:eoFill:)**：返回一个新形状，该形状或给定形状中都有填充区域。


---
source: https://developer.apple.com/documentation/SwiftUI/Shape/lineIntersection(_:eoFill:)
crawled: 2025-12-01T02:32:59Z
---

# lineIntersection(_:eoFill:)

**Instance Method**

Returns a new shape with a line from this shape that overlaps the filled regions of the given shape.

## Declaration

```swift
nonisolated func lineIntersection<T>(_ other: T, eoFill: Bool = false) -> some Shape where T : Shape

```

## Parameters

- **other**: The shape to intersect.
- **eoFill**: Whether to use the even-odd rule for determining which areas to treat as the interior of the shapes (if true), or the non-zero rule (if false).

## Return Value

A new shape.

## Discussion

The line of the resulting shape is the line of this shape that overlaps the filled region of `other`.

Intersected subpaths that are clipped create open subpaths. Closed subpaths that do not intersect `other` remain closed.

## Performing operations on a shape

- **intersection(_:eoFill:)**: Returns a new shape with filled regions common to both shapes.
- **lineSubtraction(_:eoFill:)**: Returns a new shape with a line from this shape that does not overlap the filled region of the given shape.
- **subtracting(_:eoFill:)**: Returns a new shape with filled regions from this shape that are not in the given shape.
- **symmetricDifference(_:eoFill:)**: Returns a new shape with filled regions either from this shape or the given shape, but not in both.
- **union(_:eoFill:)**: Returns a new shape with filled regions in either this shape or the given shape.

