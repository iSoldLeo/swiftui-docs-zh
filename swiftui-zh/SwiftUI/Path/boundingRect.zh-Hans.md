---
来源： https://developer.apple.com/documentation/SwiftUI/Path/boundingRect
抓取时间： 2025-12-02T21:42:19Z
---

# 边界矩形

**实例属性**

包含所有路径段的矩形。

## 声明

```swift
var boundingRect: CGRect { get }
```

## 讨论

这是完全包围路径中所有点的最小矩形，但不包括贝塞尔曲线的控制点。

## 获取路径特征

- **cgPath**：表示路径中元素的不可变路径。
- **contains(_:eoFill:)**：如果路径包含指定点，则返回 true。
- **currentPoint**：返回路径中的最后一个点，如果路径不包含任何点，则返回 nil。
- **description**：路径的描述，可用于通过`init?(_:)`重新创建路径。
- **isEmpty**：布尔值，表示路径是否包含零元素。


---
source: https://developer.apple.com/documentation/SwiftUI/Path/boundingRect
crawled: 2025-12-02T21:42:19Z
---

# boundingRect

**Instance Property**

A rectangle containing all path segments.

## Declaration

```swift
var boundingRect: CGRect { get }
```

## Discussion

This is the smallest rectangle completely enclosing all points in the path but not including control points for Bézier curves.

## Getting the path’s characteristics

- **cgPath**: An immutable path representing the elements in the path.
- **contains(_:eoFill:)**: Returns true if the path contains a specified point.
- **currentPoint**: Returns the last point in the path, or nil if the path contains no points.
- **description**: A description of the path that may be used to recreate the path via `init?(_:)`.
- **isEmpty**: A Boolean value indicating whether the path contains zero elements.

