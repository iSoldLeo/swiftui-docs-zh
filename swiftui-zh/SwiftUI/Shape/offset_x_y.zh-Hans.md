---
来源：https://developer.apple.com/documentation/SwiftUI/Shape/offset(x:y:)
抓取时间： 2025-12-02T21:41:53Z
---

# offset(x:y:)

**实例方法**

使用指定点更改此形状的相对位置。

## 声明

```swift
func offset(x: CGFloat = 0, y: CGFloat = 0) -> OffsetShape<Self>
```

## 参数

- **x**：偏移形状的水平量（以点为单位）。负数向左，正数向右。
- **y**：以点为单位，偏移形状的垂直量。负数向上，正数向下。

## 返回值

按指定数量偏移的形状。

## 讨论

下面的示例渲染了两个圆。它将一个圆置于默认位置。第二个圆用描边勾勒，位于第一个圆的上方，向左偏移 100 点，向下偏移 50 点。

```swift
Circle()
.overlay(
    Circle()
    .offset(x: -100, y: 50)
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
- **offset(_:)**：使用指定的点改变此形状的相对位置。


---
source: https://developer.apple.com/documentation/SwiftUI/Shape/offset(x:y:)
crawled: 2025-12-02T21:41:53Z
---

# offset(x:y:)

**Instance Method**

Changes the relative position of this shape using the specified point.

## Declaration

```swift
func offset(x: CGFloat = 0, y: CGFloat = 0) -> OffsetShape<Self>
```

## Parameters

- **x**: The horizontal amount, in points, by which you offset the shape. Negative numbers are to the left and positive numbers are to the right.
- **y**: The vertical amount, in points, by which you offset the shape. Negative numbers are up and positive numbers are down.

## Return Value

A shape offset by the specified amount.

## Discussion

The following example renders two circles. It places one circle at its default position. The second circle is outlined with a stroke, positioned on top of the first circle and offset by 100 points to the left and 50 points below.

```swift
Circle()
.overlay(
    Circle()
    .offset(x: -100, y: 50)
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
- **offset(_:)**: Changes the relative position of this shape using the specified point.

