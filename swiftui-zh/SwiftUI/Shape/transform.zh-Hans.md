---
来源： https://developer.apple.com/documentation/SwiftUI/Shape/transform(_:)
抓取时间： 2025-12-01T02:32:46Z
---

# transform(_:)

**实例方法**

对形状进行仿射变换。

## 声明

```swift
func transform(_ transform: CGAffineTransform) -> TransformedShape<Self>
```

## 参数

- **transform**：要应用到此形状的仿射变换矩阵。

## 返回值

根据矩阵值变换后的形状。

## 讨论

仿射变换是将旋转、缩放、平移和倾斜组合应用于形状的一种数学方法。

## 变换形状

- **trim(from:to:)**：根据形状的路径表示法，对形状进行小数点修剪。
- **size(_:)**：返回表示相同形状的新版本 self，但要求它从`size` 的矩形创建路径。这不会影响根据形状创建的任何视图的布局属性（例如通过填充）。
- **size(width:height:)**：返回表示相同形状的新版本 self，但要求它从`(width, height)` 大小的矩形中创建路径。这不会影响根据形状创建的任何视图的布局属性（例如通过填充）。
- **scale(_:anchor:)**：缩放此形状而不改变其边框。
- **scale(x:y:anchor:)**：缩放此形状而不改变其边框。
- **rotation(_:anchor:)**：以您指定的角度围绕锚点旋转此形状。
- **offset(_:)**：使用指定的点改变此形状的相对位置。
- **offset(x:y:)**：使用指定的点更改此形状的相对位置。


---
source: https://developer.apple.com/documentation/SwiftUI/Shape/transform(_:)
crawled: 2025-12-01T02:32:46Z
---

# transform(_:)

**Instance Method**

Applies an affine transform to this shape.

## Declaration

```swift
func transform(_ transform: CGAffineTransform) -> TransformedShape<Self>
```

## Parameters

- **transform**: The affine transformation matrix to apply to this shape.

## Return Value

A transformed shape, based on its matrix values.

## Discussion

Affine transforms present a mathematical approach to applying combinations of rotation, scaling, translation, and skew to shapes.

## Transforming a shape

- **trim(from:to:)**: Trims this shape by a fractional amount based on its representation as a path.
- **size(_:)**: Returns a new version of self representing the same shape, but that will ask it to create its path from a rect of `size`. This does not affect the layout properties of any views created from the shape (e.g. by filling it).
- **size(width:height:)**: Returns a new version of self representing the same shape, but that will ask it to create its path from a rect of size `(width, height)`. This does not affect the layout properties of any views created from the shape (e.g. by filling it).
- **scale(_:anchor:)**: Scales this shape without changing its bounding frame.
- **scale(x:y:anchor:)**: Scales this shape without changing its bounding frame.
- **rotation(_:anchor:)**: Rotates this shape around an anchor point at the angle you specify.
- **offset(_:)**: Changes the relative position of this shape using the specified point.
- **offset(x:y:)**: Changes the relative position of this shape using the specified point.

