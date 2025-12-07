---
来源： https://developer.apple.com/documentation/SwiftUI/Path/init(ellipseIn:)
抓取时间：2025-12-02T21:42:16Z
---

# init(ellipseIn:)

**Initializer**

在给定的矩形内创建椭圆路径。

## 声明

```swift
init(ellipseIn rect: CGRect)
```

## 参数

- **rect**：包围椭圆的矩形。

## 讨论

这是一个创建椭圆路径的便利函数。使用此函数比创建路径并添加椭圆更有效率。

椭圆由一系列贝塞尔曲线逼近。椭圆的中心是由 rect 参数定义的矩形的中点。如果矩形是正方形，那么椭圆就是半径等于矩形宽度（或高度）二分之一的圆形。如果矩形参数指定的是矩形，那么椭圆的主轴和次轴就是由矩形的宽度和高度定义的。

椭圆构成路径的完整子路径，也就是说，椭圆绘制以移动到操作开始，以关闭子路径操作结束，所有移动都按顺时针方向进行。如果您提供仿射变换，那么定义椭圆的贝塞尔曲线在添加到路径之前会进行变换。

## 创建路径

- **init()**：创建空路径。
- **init(_:)**：创建空路径，然后执行闭包添加初始元素。
- **init(roundedRect:cornerRadius:style:)**：创建包含圆角矩形的路径。
- **init(roundedRect:cornerSize:style:)**：创建包含圆角矩形的路径：创建包含圆角矩形的路径。
- **init(roundedRect:cornerRadii:style:)**：以给定的圆角矩形创建路径，圆角矩形的边角半径可能不均匀。


---
source: https://developer.apple.com/documentation/SwiftUI/Path/init(ellipseIn:)
crawled: 2025-12-02T21:42:16Z
---

# init(ellipseIn:)

**Initializer**

Creates a path as an ellipse within the given rectangle.

## Declaration

```swift
init(ellipseIn rect: CGRect)
```

## Parameters

- **rect**: The rectangle that bounds the ellipse.

## Discussion

This is a convenience function that creates a path of an ellipse. Using this convenience function is more efficient than creating a path and adding an ellipse to it.

The ellipse is approximated by a sequence of Bézier curves. Its center is the midpoint of the rectangle defined by the rect parameter. If the rectangle is square, then the ellipse is circular with a radius equal to one-half the width (or height) of the rectangle. If the rect parameter specifies a rectangular shape, then the major and minor axes of the ellipse are defined by the width and height of the rectangle.

The ellipse forms a complete subpath of the path—that is, the ellipse drawing starts with a move-to operation and ends with a close-subpath operation, with all moves oriented in the clockwise direction. If you supply an affine transform, then the constructed Bézier curves that define the ellipse are transformed before they are added to the path.

## Creating a path

- **init()**: Creates an empty path.
- **init(_:)**: Creates an empty path, then executes a closure to add its initial elements.
- **init(roundedRect:cornerRadius:style:)**: Creates a path containing a rounded rectangle.
- **init(roundedRect:cornerSize:style:)**: Creates a path containing a rounded rectangle.
- **init(roundedRect:cornerRadii:style:)**: Creates a path as the given rounded rectangle, which may have uneven corner radii.

