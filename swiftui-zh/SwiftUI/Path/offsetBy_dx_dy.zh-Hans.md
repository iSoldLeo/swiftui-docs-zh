---
来源：https://developer.apple.com/documentation/SwiftUI/Path/offsetBy(dx:dy:)
抓取时间：2025-12-01T02:33:30Z
---

# offsetBy(dx:dy:)

**实例方法**

返回通过平移所有点构建的路径。

## 声明

```swift
func offsetBy(dx: CGFloat, dy: CGFloat) -> Path
```

## 参数

- **dx**：在水平轴上应用的偏移量。
- **dy**：应用于垂直轴的偏移量。

## 返回值

路径的新副本，所有点都应用了偏移量。

## 转换路径

- **applying(_:)**：将变换应用到路径的所有点，返回一条路径。
- **trimmedPath(from:to:)**：返回路径的部分副本。


---
source: https://developer.apple.com/documentation/SwiftUI/Path/offsetBy(dx:dy:)
crawled: 2025-12-01T02:33:30Z
---

# offsetBy(dx:dy:)

**Instance Method**

Returns a path constructed by translating all its points.

## Declaration

```swift
func offsetBy(dx: CGFloat, dy: CGFloat) -> Path
```

## Parameters

- **dx**: The offset to apply in the horizontal axis.
- **dy**: The offset to apply in the vertical axis.

## Return Value

A new copy of the path with the offset applied to all points.

## Transforming the path

- **applying(_:)**: Returns a path constructed by applying the transform to all points of the path.
- **trimmedPath(from:to:)**: Returns a partial copy of the path.

