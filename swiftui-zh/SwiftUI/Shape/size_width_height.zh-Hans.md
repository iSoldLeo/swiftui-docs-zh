---
来源：https://developer.apple.com/documentation/SwiftUI/Shape/size(width:height:)
抓取时间： 2025-12-01T02:32:47Z
---

# size(width:height:)

**实例方法**

返回代表相同形状的新版本 self，但要求它从大小为 `(width, height)` 的矩形创建路径。这不会影响根据形状创建的任何视图的布局属性（例如通过填充）。

## 声明

```swift
nonisolated func size(width: CGFloat, height: CGFloat) -> some Shape

```

## 变形

- **trim(from:to:)**：根据形状的路径表示法，以分数为单位修剪该形状。
- **transform(_:)**：对该形状应用仿射变换。
- **size(_:)**：返回代表相同形状的新版本 self，但要求它从`size` 的矩形创建路径。这不会影响根据形状创建的任何视图的布局属性（例如通过填充）。
- **scale(_:anchor:)**：缩放此形状而不改变其边框。
- **scale(x:y:anchor:)**：缩放此形状而不改变其边框。
- **rotation(_:anchor:)**：以您指定的角度围绕锚点旋转此形状。
- **offset(_:)**：使用指定的点改变此形状的相对位置。
- **offset(x:y:)**：使用指定的点更改此形状的相对位置。


---
source: https://developer.apple.com/documentation/SwiftUI/Shape/size(width:height:)
crawled: 2025-12-01T02:32:47Z
---

# size(width:height:)

**Instance Method**

Returns a new version of self representing the same shape, but that will ask it to create its path from a rect of size `(width, height)`. This does not affect the layout properties of any views created from the shape (e.g. by filling it).

## Declaration

```swift
nonisolated func size(width: CGFloat, height: CGFloat) -> some Shape

```

## Transforming a shape

- **trim(from:to:)**: Trims this shape by a fractional amount based on its representation as a path.
- **transform(_:)**: Applies an affine transform to this shape.
- **size(_:)**: Returns a new version of self representing the same shape, but that will ask it to create its path from a rect of `size`. This does not affect the layout properties of any views created from the shape (e.g. by filling it).
- **scale(_:anchor:)**: Scales this shape without changing its bounding frame.
- **scale(x:y:anchor:)**: Scales this shape without changing its bounding frame.
- **rotation(_:anchor:)**: Rotates this shape around an anchor point at the angle you specify.
- **offset(_:)**: Changes the relative position of this shape using the specified point.
- **offset(x:y:)**: Changes the relative position of this shape using the specified point.

