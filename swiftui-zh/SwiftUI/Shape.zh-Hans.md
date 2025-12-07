--- 来源：https://developer.apple.com/documentation/SwiftUI/Shape
抓取时间：2025-12-02T16:22:28Z

---

# 形状

**Protocol**

可在绘制视图时使用的二维形状。

## 声明

```swift
protocol Shape : Sendable, Animatable, View, _RemoveGlobalActorIsolation
```

## 概述

未显式填充或描边的形状会根据前景色获得默认填充。

您可以根据隐式参考系（例如包含它的视图的自然大小）定义形状。或者，您可以使用绝对坐标定义形状。

## 获取标准形状

- **buttonBorder**：一种形状，其按钮边框形状由环境决定。

- **capsule**：一种胶囊形状，其与包含它的视图的框架对齐。

- **capsule(style:)**：位于包含它的视图框架内的胶囊形状。

- **circle**：位于包含它的视图框架内的圆。

- **containerRelative**：会被当前容器形状的内嵌版本替换的形状。如果未定义容器形状，则会被替换为矩形。

- **ellipse**：位于包含它的视图框架内的椭圆。

- **rect**：位于包含它的视图框架内的矩形。

- **rect(cornerRadii:style:)**：位于包含它的视图框架内的圆角矩形，圆角值各不相同。

- **rect(cornerRadius:style:)**：位于包含它的视图框架内的圆角矩形。

- **rect(cornerSize:style:)**：一个圆角矩形，位于包含它的视图框架内。

- **rect(topLeadingRadius:bottomLeadingRadius:bottomTrailingRadius:topTrailingRadius:style:)**：一个圆角矩形，具有不同的圆角值，位于包含它的视图框架内。

## 定义形状的大小和路径

- **sizeThatFits(_:)**：根据给定的大小，返回将渲染该形状的视图的大小。

- **path(in:)**：将此形状描述为矩形参考系内的路径。

## 变换形状

- **trim(from:to:)**：根据形状作为路径的表示，按一定比例修剪该形状。

- **transform(_:)**：对该形状应用仿射变换。

- **size(_:)**：返回一个表示相同形状的新版本，但该版本会要求其从 `size` 大小的矩形创建路径。这不会影响由该形状创建的任何视图的布局属性（例如，通过填充该形状）。

- **size(width:height:)**：返回一个表示相同形状的新版本，但该版本会要求其从 `(width, height)` 大小的矩形创建路径。这不会影响由该形状创建的任何视图的布局属性（例如，通过填充该形状）。

- **scale(_:anchor:)**：缩放此形状而不改变其边界框。

- **scale(x:y:anchor:)**：缩放此形状而不改变其边界框。

- **rotation(_:anchor:)**：围绕锚点以您指定的角度旋转此形状。

- **offset(_:)**：使用指定点更改此形状的相对位置。

- **offset(x:y:)**：使用指定点更改此形状的相对位置。

## 设置描边特征

- **stroke(_:lineWidth:)**：使用颜色或渐变描绘此形状的轮廓。

- **stroke(_:lineWidth:antialiased:)**：使用颜色或渐变描绘此形状的轮廓。

- **stroke(lineWidth:)**：返回一个新形状，它是 `self` 的描边副本，线宽由 `lineWidth` 定义，其他所有属性均使用 `StrokeStyle` 的默认值。

- **stroke(_:style:)**：使用颜色或渐变描绘此形状的轮廓。

- **stroke(_:style:antialiased:)**：用颜色或渐变勾勒此形状的轮廓。

- **stroke(style:)**：返回一个新形状，它是 `self` 的描边副本，描边特征由 `style` 定义。

## 填充形状

- **fill(_:style:)**：用颜色或渐变填充此形状。

- **fill(style:)**：用前景色填充此形状。

## 设置角色

- **role**：指示如何设置形状的样式。

## 指示布局方向

- **layoutDirectionBehavior**：返回此形状在不同布局方向上应使用的行为。

## 对形状执行操作

- **intersection(_:eoFill:)**：返回一个新形状，其中包含两个形状共有的填充区域。

- **lineIntersection(_:eoFill:)**：返回一个新形状，其中包含一条来自该形状且与给定形状的填充区域重叠的线段。

- **lineSubtraction(_:eoFill:)**：返回一个新形状，其中包含一条来自该形状但不与给定形状的填充区域重叠的线段。

- **subtracting(_:eoFill:)**：返回一个新形状，其中包含来自该形状但不在给定形状中的填充区域。

- **symmetricDifference(_:eoFill:)**：返回一个新形状，其中包含来自该形状或给定形状的填充区域，但不同时包含来自两者的填充区域。

- **union(_:eoFill:)**：返回一个新形状，其中包含来自该形状或给定形状的填充区域。

## 实例方法

- **size(_:anchor:)**：返回一个表示相同形状的新实例，但其边界为 `size` 的矩形，而非容器大小。

- **size(width:height:anchor:)**：返回一个表示相同形状的新实例，但其边界为 `(width, height)` 的矩形，而非容器大小。

## 类型方法

- **rect(corners:isUniform:)**：一个位于包含它的视图框架内的矩形。四个角将设置为相同的样式，可以是直角、圆角或与容器形状同心。

- **rect(topLeadingCorner:topTrailingCorner:bottomLeadingCorner:bottomTrailingCorner:)**：一个位于包含它的视图框架内的矩形。每个角都可以自定义样式，可以是直角、圆角或与容器形状同心。

- **rect(uniformBottomCorners:topLeadingCorner:topTrailingCorner:)**：一个矩形，位于包含它的视图的框架内。底部两个角将统一应用一种角样式，而顶部两个角将分别应用不同的角样式。

- **rect(uniformLeadingCorners:topTrailingCorner:bottomTrailingCorner:)**：一个矩形，位于包含它的视图的框架内。前两个角将统一应用一种角样式，而后两个角将分别应用不同的角样式。

- **rect(uniformLeadingCorners:uniformTrailingCorners:)**：一个矩形，位于包含它的视图的框架内。前两个角将统一应用一种角样式，而后两个角将统一应用另一种角样式。

- **rect(uniformTopCorners:bottomLeadingCorner:bottomTrailingCorner:)**：一个矩形，位于包含它的视图的框架内。顶部两个角将统一应用一种角样式，而底部两个角将分别应用不同的角样式。

- **rect(uniformTopCorners:uniformBottomCorners:)**：一个矩形，位于包含它的视图的框架内。顶部两个角将统一应用一种角样式，而底部两个角将统一应用另一种角样式。

- **rect(uniformTrailingCorners:topLeadingCorner:bottomLeadingCorner:)**：一个矩形，位于包含它的视图的框架内。后两个角将统一应用一种角样式，而前两个角将分别应用不同的角样式。

## 定义形状行为

- **ShapeView**：一个提供可用于绘图操作的形状的视图。

- **AnyShape**：一个已擦除形状值。

- **ShapeRole**：形状样式设置方式。

- **StrokeStyle**：描边路径的特征。

- **StrokeShapeView**：描边形状提供程序。

- **StrokeBorderShapeView**：描边形状提供程序。

- **FillStyle**：栅格化矢量形状的样式。

- **FillShapeView**：填充形状提供程序。

## 继承自

- Animatable

- Sendable

- SendableMetatype

- View

## 被继承自

- InsettableShape

- RoundedRectangularShape

## 符合的类型

- AnyShape

- ButtonBorderShape

- Capsule

- Circle

- ConcentricRectangle

- ContainerRelativeShape

- DefaultGlassEffectShape

- Ellipse

- OffsetShape

- Path

- Rectangle

- RotatedShape

- RoundedRectangle

- ScaledShape

- TransformedShape

- UnevenRoundedRectangle


---
source: https://developer.apple.com/documentation/SwiftUI/Shape
crawled: 2025-12-02T16:22:28Z
---

# Shape

**Protocol**

A 2D shape that you can use when drawing a view.

## Declaration

```swift
protocol Shape : Sendable, Animatable, View, _RemoveGlobalActorIsolation
```

## Overview

Shapes without an explicit fill or stroke get a default fill based on the foreground color.

You can define shapes in relation to an implicit frame of reference, such as the natural size of the view that contains it. Alternatively, you can define shapes in terms of absolute coordinates.

## Getting standard shapes

- **buttonBorder**: A shape that defers to the environment to determine the resolved button border shape.
- **capsule**: A capsule shape aligned inside the frame of the view containing it.
- **capsule(style:)**: A capsule shape aligned inside the frame of the view containing it.
- **circle**: A circle centered on the frame of the view containing it.
- **containerRelative**: A shape that is replaced by an inset version of the current container shape. If no container shape was defined, is replaced by a rectangle.
- **ellipse**: An ellipse aligned inside the frame of the view containing it.
- **rect**: A rectangular shape aligned inside the frame of the view containing it.
- **rect(cornerRadii:style:)**: A rectangular shape with rounded corners with different values, aligned inside the frame of the view containing it.
- **rect(cornerRadius:style:)**: A rectangular shape with rounded corners, aligned inside the frame of the view containing it.
- **rect(cornerSize:style:)**: A rectangular shape with rounded corners, aligned inside the frame of the view containing it.
- **rect(topLeadingRadius:bottomLeadingRadius:bottomTrailingRadius:topTrailingRadius:style:)**: A rectangular shape with rounded corners with different values, aligned inside the frame of the view containing it.

## Defining a shape’s size and path

- **sizeThatFits(_:)**: Returns the size of the view that will render the shape, given a proposed size.
- **path(in:)**: Describes this shape as a path within a rectangular frame of reference.

## Transforming a shape

- **trim(from:to:)**: Trims this shape by a fractional amount based on its representation as a path.
- **transform(_:)**: Applies an affine transform to this shape.
- **size(_:)**: Returns a new version of self representing the same shape, but that will ask it to create its path from a rect of `size`. This does not affect the layout properties of any views created from the shape (e.g. by filling it).
- **size(width:height:)**: Returns a new version of self representing the same shape, but that will ask it to create its path from a rect of size `(width, height)`. This does not affect the layout properties of any views created from the shape (e.g. by filling it).
- **scale(_:anchor:)**: Scales this shape without changing its bounding frame.
- **scale(x:y:anchor:)**: Scales this shape without changing its bounding frame.
- **rotation(_:anchor:)**: Rotates this shape around an anchor point at the angle you specify.
- **offset(_:)**: Changes the relative position of this shape using the specified point.
- **offset(x:y:)**: Changes the relative position of this shape using the specified point.

## Setting the stroke characteristics

- **stroke(_:lineWidth:)**: Traces the outline of this shape with a color or gradient.
- **stroke(_:lineWidth:antialiased:)**: Traces the outline of this shape with a color or gradient.
- **stroke(lineWidth:)**: Returns a new shape that is a stroked copy of `self` with line-width defined by `lineWidth` and all other properties of `StrokeStyle` having their default values.
- **stroke(_:style:)**: Traces the outline of this shape with a color or gradient.
- **stroke(_:style:antialiased:)**: Traces the outline of this shape with a color or gradient.
- **stroke(style:)**: Returns a new shape that is a stroked copy of `self`, using the contents of `style` to define the stroke characteristics.

## Filling a shape

- **fill(_:style:)**: Fills this shape with a color or gradient.
- **fill(style:)**: Fills this shape with the foreground color.

## Setting the role

- **role**: An indication of how to style a shape.

## Indicating a layout direction

- **layoutDirectionBehavior**: Returns the behavior this shape should use for different layout directions.

## Performing operations on a shape

- **intersection(_:eoFill:)**: Returns a new shape with filled regions common to both shapes.
- **lineIntersection(_:eoFill:)**: Returns a new shape with a line from this shape that overlaps the filled regions of the given shape.
- **lineSubtraction(_:eoFill:)**: Returns a new shape with a line from this shape that does not overlap the filled region of the given shape.
- **subtracting(_:eoFill:)**: Returns a new shape with filled regions from this shape that are not in the given shape.
- **symmetricDifference(_:eoFill:)**: Returns a new shape with filled regions either from this shape or the given shape, but not in both.
- **union(_:eoFill:)**: Returns a new shape with filled regions in either this shape or the given shape.

## Instance Methods

- **size(_:anchor:)**: Returns a new version of self representing the same shape, but within a rect of `size` instead of the container size.
- **size(width:height:anchor:)**: Returns a new version of self representing the same shape, but within a rect of `(width, height)` instead of the container size.

## Type Methods

- **rect(corners:isUniform:)**: A rectangle shape that is aligned inside the frame of the view containing it. The same corner style will be set on four corners to be square, rounded, or concentric to the container shape.
- **rect(topLeadingCorner:topTrailingCorner:bottomLeadingCorner:bottomTrailingCorner:)**: A rectangle shape that is aligned inside the frame of the view containing it. Each of the corners can be customized in style to be square, rounded, or concentric to the container shape.
- **rect(uniformBottomCorners:topLeadingCorner:topTrailingCorner:)**: A rectangle shape that is aligned inside the frame of the view containing it. A corner style will be uniformly applied to the bottom two corners, while the top two corners will each has an indivdual corner style.
- **rect(uniformLeadingCorners:topTrailingCorner:bottomTrailingCorner:)**: A rectangle shape that is aligned inside the frame of the view containing it. A corner style will be uniformly applied to the leading two corners, while the trailing two corners will each has an indivdual corner style.
- **rect(uniformLeadingCorners:uniformTrailingCorners:)**: A rectangle shape that is aligned inside the frame of the view containing it. A corner style will be uniformly applied to the leading two corners, while another corner style will be uniformly applied to the trailing two.
- **rect(uniformTopCorners:bottomLeadingCorner:bottomTrailingCorner:)**: A rectangle shape that is aligned inside the frame of the view containing it. A corner style will be uniformly applied to the top two corners, while the bottom two corners will each has an indivdual corner style.
- **rect(uniformTopCorners:uniformBottomCorners:)**: A rectangle shape that is aligned inside the frame of the view containing it. A corner style will be uniformly applied to the top two corners, while another corner style will be uniformly applied to the bottom two.
- **rect(uniformTrailingCorners:topLeadingCorner:bottomLeadingCorner:)**: A rectangle shape that is aligned inside the frame of the view containing it. A corner style will be uniformly applied to the trailing two corners, while the leading two corners will each has an indivdual corner style.

## Defining shape behavior

- **ShapeView**: A view that provides a shape that you can use for drawing operations.
- **AnyShape**: A type-erased shape value.
- **ShapeRole**: Ways of styling a shape.
- **StrokeStyle**: The characteristics of a stroke that traces a path.
- **StrokeShapeView**: A shape provider that strokes its shape.
- **StrokeBorderShapeView**: A shape provider that strokes the border of its shape.
- **FillStyle**: A style for rasterizing vector shapes.
- **FillShapeView**: A shape provider that fills its shape.

## Inherits From

- Animatable
- Sendable
- SendableMetatype
- View

## Inherited By

- InsettableShape
- RoundedRectangularShape

## Conforming Types

- AnyShape
- ButtonBorderShape
- Capsule
- Circle
- ConcentricRectangle
- ContainerRelativeShape
- DefaultGlassEffectShape
- Ellipse
- OffsetShape
- Path
- Rectangle
- RotatedShape
- RoundedRectangle
- ScaledShape
- TransformedShape
- UnevenRoundedRectangle

