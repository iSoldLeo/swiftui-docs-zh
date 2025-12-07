---
来源：https://developer.apple.com/documentation/SwiftUI/Path/trimmedPath(from:to:)
抓取时间： 2025-12-02T21:42:37Z
---

# trimmedPath(from:to:)

**实例方法**

返回路径的部分副本。

## 声明

```swift
func trimmedPath(from: CGFloat, to: CGFloat) -> Path
```

## 讨论

返回的路径包含`from` 和 `to`之间的区域，这两个值都必须是零到一之间的分数，定义沿路径线性插值的点。

## 转换路径

- **applying(_:)**：返回对路径上所有点进行变换后得到的路径。
- **offsetBy(dx:dy:)**：返回一条通过平移所有点构造的路径。


---
source: https://developer.apple.com/documentation/SwiftUI/Path/trimmedPath(from:to:)
crawled: 2025-12-02T21:42:37Z
---

# trimmedPath(from:to:)

**Instance Method**

Returns a partial copy of the path.

## Declaration

```swift
func trimmedPath(from: CGFloat, to: CGFloat) -> Path
```

## Discussion

The returned path contains the region between `from` and `to`, both of which must be fractions between zero and one defining points linearly-interpolated along the path.

## Transforming the path

- **applying(_:)**: Returns a path constructed by applying the transform to all points of the path.
- **offsetBy(dx:dy:)**: Returns a path constructed by translating all its points.

