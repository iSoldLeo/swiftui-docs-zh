---
来源： https://developer.apple.com/documentation/SwiftUI/Shape/rotation(_:anchor:)
抓取时间： 2025-12-02T21:41:51Z
---

# rotation(_:anchor:)

**实例方法**

以您指定的角度围绕锚点旋转此形状。

## 声明

```swift
func rotation(_ angle: Angle, anchor: UnitPoint = .center) -> RotatedShape<Self>
```

## 参数

- **angle**：要应用的旋转角度。正角顺时针旋转，负角逆时针旋转。
- **anchor**：要围绕形状旋转的点。

## 返回值

旋转后的形状。

## 讨论

下面的示例将一个正方形向右旋转 45 度，创建了一个菱形：

```swift
RoundedRectangle(cornerRadius: 10)
.rotation(Angle(degrees: 45))
.aspectRatio(1.0, contentMode: .fit)
```

## 变换形状

- **trim(from:to:)**：根据形状的路径表示法，对形状进行小数点修剪。
- **transform(_:)**：对该形状应用仿射变换。
- **size(_:)**：返回代表相同形状的新版本的 self，但会要求它从`size` 的矩形创建路径。这不会影响根据形状创建的任何视图的布局属性（例如通过填充）。
- **size(width:height:)**：返回表示相同形状的新版本 self，但要求它从`(width, height)` 大小的矩形中创建路径。这不会影响根据形状创建的任何视图的布局属性（例如通过填充）。
- **scale(_:anchor:)**：缩放此形状而不改变其边框。
- **scale(x:y:anchor:)**：缩放此形状而不改变其边框。
- **offset(_:)**：使用指定的点更改此形状的相对位置。
- **offset(x:y:)**：使用指定的点更改此形状的相对位置。


---
source: https://developer.apple.com/documentation/SwiftUI/Shape/rotation(_:anchor:)
crawled: 2025-12-02T21:41:51Z
---

# rotation(_:anchor:)

**Instance Method**

Rotates this shape around an anchor point at the angle you specify.

## Declaration

```swift
func rotation(_ angle: Angle, anchor: UnitPoint = .center) -> RotatedShape<Self>
```

## Parameters

- **angle**: The angle of rotation to apply. Positive angles rotate clockwise; negative angles rotate counterclockwise.
- **anchor**: The point to rotate the shape around.

## Return Value

A rotated shape.

## Discussion

The following example rotates a square by 45 degrees to the right to create a diamond shape:

```swift
RoundedRectangle(cornerRadius: 10)
.rotation(Angle(degrees: 45))
.aspectRatio(1.0, contentMode: .fit)
```

## Transforming a shape

- **trim(from:to:)**: Trims this shape by a fractional amount based on its representation as a path.
- **transform(_:)**: Applies an affine transform to this shape.
- **size(_:)**: Returns a new version of self representing the same shape, but that will ask it to create its path from a rect of `size`. This does not affect the layout properties of any views created from the shape (e.g. by filling it).
- **size(width:height:)**: Returns a new version of self representing the same shape, but that will ask it to create its path from a rect of size `(width, height)`. This does not affect the layout properties of any views created from the shape (e.g. by filling it).
- **scale(_:anchor:)**: Scales this shape without changing its bounding frame.
- **scale(x:y:anchor:)**: Scales this shape without changing its bounding frame.
- **offset(_:)**: Changes the relative position of this shape using the specified point.
- **offset(x:y:)**: Changes the relative position of this shape using the specified point.

