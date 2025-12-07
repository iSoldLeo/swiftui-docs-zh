---
来源： https://developer.apple.com/documentation/SwiftUI/Shape/offset(_:)
抓取时间： 2025-12-02T21:41:52Z
---

# offset(_:)

**实例方法**

使用指定点改变此形状的相对位置。

## 声明

```swift
func offset(_ offset: CGPoint) -> OffsetShape<Self>
```

## 参数

- **offset**：偏移形状的点数。负数表示向左和向上偏移；正数表示向右和向下偏移。

## 返回值

按指定点数偏移的形状。

## 讨论

下面的示例渲染了两个圆。它将一个圆置于默认位置。第二个圆用描边勾勒，位于第一个圆的上方，向左偏移 100 点，向下偏移 50 点。

```swift
Circle()
.overlay(
    Circle()
    .offset(CGPoint(x: -100, y: 50))
    .stroke()
)
```

## 变换形状

- **trim(from:to:)**：根据形状的路径表示法，对形状进行小数点修剪。
- **transform(_:)**：对该形状应用仿射变换。
- **size(_:)**：返回代表相同形状的新版本 self，但要求它从`size` 的矩形创建路径。这不会影响根据形状创建的任何视图的布局属性（例如通过填充）。
- **size(width:height:)**：返回表示相同形状的新版本 self，但要求它从`(width, height)` 大小的矩形中创建路径。这不会影响根据形状创建的任何视图的布局属性（例如通过填充）。
- **scale(_:anchor:)**：缩放此形状而不改变其边框。
- **scale(x:y:anchor:)**：缩放此形状而不改变其边框。
- **rotation(_:anchor:)**：以您指定的角度围绕锚点旋转此形状。
- **offset(x:y:)**：使用指定的点改变此形状的相对位置。


---
source: https://developer.apple.com/documentation/SwiftUI/Shape/offset(_:)
crawled: 2025-12-02T21:41:52Z
---

# offset(_:)

**Instance Method**

Changes the relative position of this shape using the specified point.

## Declaration

```swift
func offset(_ offset: CGPoint) -> OffsetShape<Self>
```

## Parameters

- **offset**: The amount, in points, by which you offset the shape. Negative numbers are to the left and up; positive numbers are to the right and down.

## Return Value

A shape offset by the specified amount.

## Discussion

The following example renders two circles. It places one circle at its default position. The second circle is outlined with a stroke, positioned on top of the first circle and offset by 100 points to the left and 50 points below.

```swift
Circle()
.overlay(
    Circle()
    .offset(CGPoint(x: -100, y: 50))
    .stroke()
)
```

## Transforming a shape

- **trim(from:to:)**: Trims this shape by a fractional amount based on its representation as a path.
- **transform(_:)**: Applies an affine transform to this shape.
- **size(_:)**: Returns a new version of self representing the same shape, but that will ask it to create its path from a rect of `size`. This does not affect the layout properties of any views created from the shape (e.g. by filling it).
- **size(width:height:)**: Returns a new version of self representing the same shape, but that will ask it to create its path from a rect of size `(width, height)`. This does not affect the layout properties of any views created from the shape (e.g. by filling it).
- **scale(_:anchor:)**: Scales this shape without changing its bounding frame.
- **scale(x:y:anchor:)**: Scales this shape without changing its bounding frame.
- **rotation(_:anchor:)**: Rotates this shape around an anchor point at the angle you specify.
- **offset(x:y:)**: Changes the relative position of this shape using the specified point.

