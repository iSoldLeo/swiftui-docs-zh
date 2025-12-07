---
来源： https://developer.apple.com/documentation/SwiftUI/Path/applying(_:)
抓取时间： 2025-12-01T02:33:29Z
---

# 应用(_:)

**实例方法**

将变换应用于路径上的所有点，返回一条路径。

## 声明

```swift
func applying(_ transform: CGAffineTransform) -> Path
```

## 参数

- **transform**：要应用于路径的仿射变换。

## 返回值

路径的新副本，所有点都应用了变换。

## 路径变换

- **offsetBy(dx:dy:)**：返回将所有点平移后的路径。
- **trimmedPath(from:to:)**：返回路径的部分副本。


---
source: https://developer.apple.com/documentation/SwiftUI/Path/applying(_:)
crawled: 2025-12-01T02:33:29Z
---

# applying(_:)

**Instance Method**

Returns a path constructed by applying the transform to all points of the path.

## Declaration

```swift
func applying(_ transform: CGAffineTransform) -> Path
```

## Parameters

- **transform**: An affine transform to apply to the path.

## Return Value

A new copy of the path with the transform applied to all points.

## Transforming the path

- **offsetBy(dx:dy:)**: Returns a path constructed by translating all its points.
- **trimmedPath(from:to:)**: Returns a partial copy of the path.

