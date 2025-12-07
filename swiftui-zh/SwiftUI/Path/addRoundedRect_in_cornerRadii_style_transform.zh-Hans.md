---
来源：https://developer.apple.com/documentation/SwiftUI/Path/addRoundedRect(in:cornerRadii:style:transform:)
抓取时间：2025-12-02T21:42:46Z
---

# addRoundedRect(in:cornerRadii:style:transform:)

**实例方法**

为路径添加一个边角不平整的圆角矩形。

## 声明

```swift
mutating func addRoundedRect(in rect: CGRect, cornerRadii: RectangleCornerRadii, style: RoundedCornerStyle = .continuous, transform: CGAffineTransform = .identity)
```

## 参数

- **rect**：以用户空间坐标指定的矩形。
- **cornerRadii**：矩形每个角的半径，以用户空间坐标指定。
- **style**：角的样式。如果未指定，默认为`continous`样式。
- **transform**：在添加到路径之前应用于矩形的仿射变换。如果未指定，默认为标识变换。

## 讨论

这是一个将圆角矩形添加到路径的便捷函数，首先移动到右边缘的中心，然后逆时针添加线条和曲线以创建圆角矩形，最后关闭子路径。


---
source: https://developer.apple.com/documentation/SwiftUI/Path/addRoundedRect(in:cornerRadii:style:transform:)
crawled: 2025-12-02T21:42:46Z
---

# addRoundedRect(in:cornerRadii:style:transform:)

**Instance Method**

Adds a rounded rectangle with uneven corners to the path.

## Declaration

```swift
mutating func addRoundedRect(in rect: CGRect, cornerRadii: RectangleCornerRadii, style: RoundedCornerStyle = .continuous, transform: CGAffineTransform = .identity)
```

## Parameters

- **rect**: A rectangle, specified in user space coordinates.
- **cornerRadii**: The radius of each corner of the rectangle, specified in user space coordinates.
- **style**: The corner style. Defaults to the `continous` style if not specified.
- **transform**: An affine transform to apply to the rectangle before adding to the path. Defaults to the identity transform if not specified.

## Discussion

This is a convenience function that adds a rounded rectangle to a path, starting by moving to the center of the right edge and then adding lines and curves counter-clockwise to create a rounded rectangle, closing the subpath.

