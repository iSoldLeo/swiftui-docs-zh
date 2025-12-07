---
来源： https://developer.apple.com/documentation/SwiftUI/Path/currentPoint
抓取时间： 2025-12-02T21:42:21Z
---

# 当前点

**实例属性**

返回路径中的最后一个点，如果路径中没有点，则返回 nil。

## 声明

```swift
var currentPoint: CGPoint? { get }
```

## 获取路径特征

- **boundingRect**：包含所有路径段的矩形。
- **cgPath**：表示路径中元素的不可变路径。
- **contains(_:eoFill:)**：如果路径包含指定点，则返回 true。
- **description**：路径的描述，可用于通过`init?(_:)`重新创建路径。
- **isEmpty**：布尔值，表示路径是否包含零元素。


---
source: https://developer.apple.com/documentation/SwiftUI/Path/currentPoint
crawled: 2025-12-02T21:42:21Z
---

# currentPoint

**Instance Property**

Returns the last point in the path, or nil if the path contains no points.

## Declaration

```swift
var currentPoint: CGPoint? { get }
```

## Getting the path’s characteristics

- **boundingRect**: A rectangle containing all path segments.
- **cgPath**: An immutable path representing the elements in the path.
- **contains(_:eoFill:)**: Returns true if the path contains a specified point.
- **description**: A description of the path that may be used to recreate the path via `init?(_:)`.
- **isEmpty**: A Boolean value indicating whether the path contains zero elements.

