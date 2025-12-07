---
来源：https://developer.apple.com/documentation/SwiftUI/Path/symmetricDifference(_:eoFill:)
抓取时间： 2025-12-01T02:33:35Z
---

# symmetricDifference(_:eoFill:)

**实例方法**

返回一条新路径，其中的填充区域要么来自本路径，要么来自给定路径，但不能同时来自两个路径。

## 声明

```swift
func symmetricDifference(_ other: Path, eoFill: Bool = false) -> Path
```

## 参数

- **other**：通向差异的路径。
- **eoFill**：是使用偶数规则（如果为真），还是使用非零规则（如果为假）来决定将哪些区域作为路径的内部区域。

## 返回值

一条新路径。

## 讨论

生成路径的填充区域是本路径或`other` 中包含的填充区域，而不是两者都包含。

任一路径中任何未封闭的子路径都被假定为封闭的。使用偶数填充规则或非零填充规则填充这条路径的结果是相同的。

## 对路径执行操作

- **addRoundedRect(in:cornerSize:style:transform:)**：为路径添加一个圆角矩形。
- **intersection(_:eoFill:)**：返回一条新路径，其中包含两条路径共有的填充区域。
- **lineIntersection(_:eoFill:)**：返回一条新路径，该路径的一条直线与给定路径的填充区域重叠。
- **lineSubtraction(_:eoFill:)**：返回一条新路径，该路径的直线不会与给定路径的填充区域重叠。
- **normalized(eoFill:)**：返回此路径的一个新的弱简单副本。
- **subtracting(_:eoFill:)**：返回一条新路径，其中包含此路径中已填充但未在给定路径中的区域。
- **union(_:eoFill:)**：返回一条新路径，其中包含此路径或给定路径中的填充区域。


---
source: https://developer.apple.com/documentation/SwiftUI/Path/symmetricDifference(_:eoFill:)
crawled: 2025-12-01T02:33:35Z
---

# symmetricDifference(_:eoFill:)

**Instance Method**

Returns a new path with filled regions either from this path or the given path, but not in both.

## Declaration

```swift
func symmetricDifference(_ other: Path, eoFill: Bool = false) -> Path
```

## Parameters

- **other**: The path to difference.
- **eoFill**: Whether to use the even-odd rule for determining which areas to treat as the interior of the paths (if true), or the non-zero rule (if false).

## Return Value

A new path.

## Discussion

The filled region of the resulting path is the filled region contained in either this path or `other`, but not both.

Any unclosed subpaths in either path are assumed to be closed. The result of filling this path using either even-odd or non-zero fill rules is identical.

## Performing operations on the path

- **addRoundedRect(in:cornerSize:style:transform:)**: Adds a rounded rectangle to the path.
- **intersection(_:eoFill:)**: Returns a new path with filled regions common to both paths.
- **lineIntersection(_:eoFill:)**: Returns a new path with a line from this path that overlaps the filled regions of the given path.
- **lineSubtraction(_:eoFill:)**: Returns a new path with a line from this path that does not overlap the filled region of the given path.
- **normalized(eoFill:)**: Returns a new weakly-simple copy of this path.
- **subtracting(_:eoFill:)**: Returns a new path with filled regions from this path that are not in the given path.
- **union(_:eoFill:)**: Returns a new path with filled regions in either this path or the given path.

