---
来源：https://developer.apple.com/documentation/SwiftUI/Shape/scale(x:y:anchor:)
抓取时间：2025-12-01T02:32:48Z
---

# scale(x:y:anchor:)

**实例方法**

在不改变包围帧的情况下缩放此形状。

## 声明

```swift
func scale(x: CGFloat = 1, y: CGFloat = 1, anchor: UnitPoint = .center) -> ScaledShape<Self>
```

## 参数

- **x**：用于沿 x 轴调整此形状大小的乘法因子。
- **y**：用于沿 Y 轴调整此形状大小的乘法因子。

## 返回值

此形状的缩放形式。

## 讨论

`x`和`y`乘法因子在设置为`0.5`时都会将各自维度的大小减半、设置为 `1` 时，其尺寸保持现有大小；设置为 `2` 时，其尺寸加倍，依此类推。

## 变换形状

- **trim(from:to:)**：根据该形状的路径表示法，对其进行小数点修剪。
- **transform(_:)**：对该形状应用仿射变换。
- **size(_:)**：返回代表相同形状的新版本 self，但要求它从`size` 的矩形创建路径。这不会影响根据形状创建的任何视图的布局属性（例如通过填充）。
- **size(width:height:)**：返回表示相同形状的新版本 self，但要求它从`(width, height)` 大小的矩形中创建路径。这不会影响根据形状创建的任何视图的布局属性（例如通过填充）。
- **scale(_:anchor:)**：缩放此形状，但不改变其边框。
- **rotation(_:anchor:)**：以您指定的角度围绕锚点旋转此形状。
- **offset(_:)**：使用指定的点改变此形状的相对位置。
- **offset(x:y:)**：使用指定的点更改此形状的相对位置。


---
source: https://developer.apple.com/documentation/SwiftUI/Shape/scale(x:y:anchor:)
crawled: 2025-12-01T02:32:48Z
---

# scale(x:y:anchor:)

**Instance Method**

Scales this shape without changing its bounding frame.

## Declaration

```swift
func scale(x: CGFloat = 1, y: CGFloat = 1, anchor: UnitPoint = .center) -> ScaledShape<Self>
```

## Parameters

- **x**: The multiplication factor used to resize this shape along its x-axis.
- **y**: The multiplication factor used to resize this shape along its y-axis.

## Return Value

A scaled form of this shape.

## Discussion

Both the `x` and `y` multiplication factors halve their respective dimension’s size when set to `0.5`, maintain their existing size when set to `1`, double their size when set to `2`, and so forth.

## Transforming a shape

- **trim(from:to:)**: Trims this shape by a fractional amount based on its representation as a path.
- **transform(_:)**: Applies an affine transform to this shape.
- **size(_:)**: Returns a new version of self representing the same shape, but that will ask it to create its path from a rect of `size`. This does not affect the layout properties of any views created from the shape (e.g. by filling it).
- **size(width:height:)**: Returns a new version of self representing the same shape, but that will ask it to create its path from a rect of size `(width, height)`. This does not affect the layout properties of any views created from the shape (e.g. by filling it).
- **scale(_:anchor:)**: Scales this shape without changing its bounding frame.
- **rotation(_:anchor:)**: Rotates this shape around an anchor point at the angle you specify.
- **offset(_:)**: Changes the relative position of this shape using the specified point.
- **offset(x:y:)**: Changes the relative position of this shape using the specified point.

