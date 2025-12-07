---
来源：https://developer.apple.com/documentation/SwiftUI/Path/normalized(eoFill:)
抓取时间： 2025-12-01T02:33:34Z
---

# normalized(eoFill:)

**实例方法**

返回此路径的一个新的弱简单副本。

## 声明

```swift
func normalized(eoFill: Bool = true) -> Path
```

## 参数

- **eoFill**：是使用偶数规则（如果为 true），还是使用非零规则（如果为 false）来决定将哪些区域作为路径的内部区域。

## 返回值

一条新路径。

## 讨论

返回的路径是一条弱简单路径，没有自交点，并且方向正常。使用偶数填充规则或非零填充规则填充这条路径的结果是相同的。

## 对路径进行操作

- **addRoundedRect(in:cornerSize:style:transform:)**：为路径添加一个圆角矩形。
- **intersection(_:eoFill:)**：返回一条新路径，其中包含两条路径共有的填充区域。
- **lineIntersection(_:eoFill:)**：返回一条新路径，该路径的一条直线与给定路径的填充区域重叠。
- **lineSubtraction(_:eoFill:)**：返回一条新路径，该路径的直线不会与给定路径的填充区域重叠。
- **subtracting(_:eoFill:)**：返回一条新路径，该路径的填充区域不在给定路径中。
- **symmetricDifference(_:eoFill:)**：返回一条新路径，其中的填充区域要么来自此路径，要么来自给定路径，但不会同时来自这两条路径。
- **union(_:eoFill:)**：返回一条新路径，该路径或给定路径中都有填充区域。


---
source: https://developer.apple.com/documentation/SwiftUI/Path/normalized(eoFill:)
crawled: 2025-12-01T02:33:34Z
---

# normalized(eoFill:)

**Instance Method**

Returns a new weakly-simple copy of this path.

## Declaration

```swift
func normalized(eoFill: Bool = true) -> Path
```

## Parameters

- **eoFill**: Whether to use the even-odd rule for determining which areas to treat as the interior of the paths (if true), or the non-zero rule (if false).

## Return Value

A new path.

## Discussion

The returned path is a weakly-simple path, has no self-intersections, and has a normalized orientation. The result of filling this path using either even-odd or non-zero fill rules is identical.

## Performing operations on the path

- **addRoundedRect(in:cornerSize:style:transform:)**: Adds a rounded rectangle to the path.
- **intersection(_:eoFill:)**: Returns a new path with filled regions common to both paths.
- **lineIntersection(_:eoFill:)**: Returns a new path with a line from this path that overlaps the filled regions of the given path.
- **lineSubtraction(_:eoFill:)**: Returns a new path with a line from this path that does not overlap the filled region of the given path.
- **subtracting(_:eoFill:)**: Returns a new path with filled regions from this path that are not in the given path.
- **symmetricDifference(_:eoFill:)**: Returns a new path with filled regions either from this path or the given path, but not in both.
- **union(_:eoFill:)**: Returns a new path with filled regions in either this path or the given path.

