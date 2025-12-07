---
来源：https://developer.apple.com/documentation/SwiftUI/Path/init(roundedRect:cornerRadii:style:)
抓取时间：2025-12-01T02:33:15Z
---

# init(roundedRect:cornerRadii:style:)

**Initializer**

以给定的圆角矩形创建路径，圆角矩形的边角半径可能不均匀。

## 声明

```swift
init(roundedRect rect: CGRect, cornerRadii: RectangleCornerRadii, style: RoundedCornerStyle = .continuous)
```

## 参数

- **rect**：以用户空间坐标指定的矩形。
- **cornerRadii**：矩形每个角的半径，以用户空间坐标指定。
- **style**：角的样式。如果未指定，默认为`continous`样式。

## 讨论

这是一个创建圆角矩形路径的方便函数。使用此函数比创建路径并添加圆角矩形更有效。

## 创建路径

- **init()**：创建空路径。
- **init(_:)**：创建空路径，然后执行闭包添加初始元素。
- **init(ellipseIn:)**：在给定的矩形内以椭圆的形式创建路径。
- **init(roundedRect:cornerRadius:style:)**：创建包含圆角矩形的路径。
- **init(roundedRect:cornerSize:style:)**：创建包含圆角矩形的路径。


---
source: https://developer.apple.com/documentation/SwiftUI/Path/init(roundedRect:cornerRadii:style:)
crawled: 2025-12-01T02:33:15Z
---

# init(roundedRect:cornerRadii:style:)

**Initializer**

Creates a path as the given rounded rectangle, which may have uneven corner radii.

## Declaration

```swift
init(roundedRect rect: CGRect, cornerRadii: RectangleCornerRadii, style: RoundedCornerStyle = .continuous)
```

## Parameters

- **rect**: A rectangle, specified in user space coordinates.
- **cornerRadii**: The radius of each corner of the rectangle, specified in user space coordinates.
- **style**: The corner style. Defaults to the `continous` style if not specified.

## Discussion

This is a convenience function that creates a path of a rounded rectangle. Using this function is more efficient than creating a path and adding a rounded rectangle to it.

## Creating a path

- **init()**: Creates an empty path.
- **init(_:)**: Creates an empty path, then executes a closure to add its initial elements.
- **init(ellipseIn:)**: Creates a path as an ellipse within the given rectangle.
- **init(roundedRect:cornerRadius:style:)**: Creates a path containing a rounded rectangle.
- **init(roundedRect:cornerSize:style:)**: Creates a path containing a rounded rectangle.

