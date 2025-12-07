---
来源： https://developer.apple.com/documentation/SwiftUI/Shape/scale(_:anchor:)
抓取时间： 2025-12-02T21:41:50Z
---

# scale(_:anchor:)

**实例方法**

在不改变包围帧的情况下缩放此形状。

## 声明

```swift
func scale(_ scale: CGFloat, anchor: UnitPoint = .center) -> ScaledShape<Self>
```

## 参数

- **scale**：用于调整此形状大小的乘法因子。`0`的值会将形状缩放为无尺寸，`0.5`会将两个维度的尺寸缩放为原来的一半，`2`会将尺寸缩放为原来的两倍，以此类推。

## 返回值

此形状的缩放形式。

## 变换形状

- **trim(from:to:)**：根据路径的表示方法，对形状进行小数点修剪。
- **transform(_:)**：对该形状应用仿射变换。
- **size(_:)**：返回代表相同形状的新版本 self，但要求它从`size` 的矩形创建路径。这不会影响根据形状创建的任何视图的布局属性（例如通过填充）。
- **size(width:height:)**：返回表示相同形状的新版本 self，但要求它从`(width, height)` 大小的矩形中创建路径。这不会影响根据形状创建的任何视图的布局属性（例如通过填充）。
- **scale(x:y:anchor:)**：缩放此形状而不改变其边框。
- **rotation(_:anchor:)**：按照您指定的角度围绕锚点旋转此形状。
- **offset(_:)**：使用指定的点改变此形状的相对位置。
- **offset(x:y:)**：使用指定的点更改此形状的相对位置。


---
source: https://developer.apple.com/documentation/SwiftUI/Shape/scale(_:anchor:)
crawled: 2025-12-02T21:41:50Z
---

# scale(_:anchor:)

**Instance Method**

Scales this shape without changing its bounding frame.

## Declaration

```swift
func scale(_ scale: CGFloat, anchor: UnitPoint = .center) -> ScaledShape<Self>
```

## Parameters

- **scale**: The multiplication factor used to resize this shape. A value of `0` scales the shape to have no size, `0.5` scales to half size in both dimensions, `2` scales to twice the regular size, and so on.

## Return Value

A scaled form of this shape.

## Transforming a shape

- **trim(from:to:)**: Trims this shape by a fractional amount based on its representation as a path.
- **transform(_:)**: Applies an affine transform to this shape.
- **size(_:)**: Returns a new version of self representing the same shape, but that will ask it to create its path from a rect of `size`. This does not affect the layout properties of any views created from the shape (e.g. by filling it).
- **size(width:height:)**: Returns a new version of self representing the same shape, but that will ask it to create its path from a rect of size `(width, height)`. This does not affect the layout properties of any views created from the shape (e.g. by filling it).
- **scale(x:y:anchor:)**: Scales this shape without changing its bounding frame.
- **rotation(_:anchor:)**: Rotates this shape around an anchor point at the angle you specify.
- **offset(_:)**: Changes the relative position of this shape using the specified point.
- **offset(x:y:)**: Changes the relative position of this shape using the specified point.

