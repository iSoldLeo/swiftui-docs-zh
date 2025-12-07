---
来源：https://developer.apple.com/documentation/SwiftUI/Path/contains(_:eoFill:)
抓取时间： 2025-12-01T02:33:17Z
---

# contains(_:eoFill:)

**实例方法**

如果路径包含指定点，则返回 true。

## 声明

```swift
func contains(_ p: CGPoint, eoFill: Bool = false) -> Bool
```

## 讨论

如果 `eoFill` 为真，此方法使用偶数规则来定义哪些点在路径内。否则，它将使用非零规则。

## 获取路径特征

- **boundingRect**：包含所有路径段的矩形。
- **cgPath**：表示路径中元素的不可变路径。
- **currentPoint**：返回路径中的最后一个点，如果路径中没有点，则返回 nil。
- **description**：路径的描述，可用于通过`init?(_:)`重新创建路径。
- **isEmpty**：布尔值，表示路径是否包含零元素。


---
source: https://developer.apple.com/documentation/SwiftUI/Path/contains(_:eoFill:)
crawled: 2025-12-01T02:33:17Z
---

# contains(_:eoFill:)

**Instance Method**

Returns true if the path contains a specified point.

## Declaration

```swift
func contains(_ p: CGPoint, eoFill: Bool = false) -> Bool
```

## Discussion

If `eoFill` is true, this method uses the even-odd rule to define which points are inside the path. Otherwise, it uses the non-zero rule.

## Getting the path’s characteristics

- **boundingRect**: A rectangle containing all path segments.
- **cgPath**: An immutable path representing the elements in the path.
- **currentPoint**: Returns the last point in the path, or nil if the path contains no points.
- **description**: A description of the path that may be used to recreate the path via `init?(_:)`.
- **isEmpty**: A Boolean value indicating whether the path contains zero elements.

