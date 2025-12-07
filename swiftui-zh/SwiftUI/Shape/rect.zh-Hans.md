---
来源： https://developer.apple.com/documentation/SwiftUI/Shape/rect
抓取时间： 2025-12-02T21:41:42Z
---

# rect

**类型属性**

在视图框架内对齐的矩形。

## 声明

```swift
static var rect: Rectangle { get }
```

## 获取标准形状

- **buttonBorder**：一种形状，它服从环境来确定已解决的按钮边框形状。
- **capsule**：在包含它的视图框架内对齐的胶囊形状。
- **capsule(style:)**：在包含它的视图框架内对齐的胶囊形状。
- **circle**：以包含它的视图框架为中心的圆。
- **containerRelative**：由当前容器形状的嵌入版本替换的形状。如果没有定义容器形状，则被矩形替换。
- **ellipse**：在包含它的视图框架内对齐的椭圆。
- **rect(cornerRadii:style:)**：一个矩形，带有不同值的圆角，在包含该矩形的视图框架内对齐。
- **rect(cornerRadius:style:)**：带圆角的矩形，在包含它的视图框架内对齐。
- **rect(cornerSize:style:)**：带圆角的矩形，在包含它的视图的边框内对齐。
- **rect(topLeadingRadius:bottomLeadingRadius:bottomTrailingRadius:topTrailingRadius:style:)**：带有不同值的圆角矩形，在包含该矩形的视图框架内对齐。


---
source: https://developer.apple.com/documentation/SwiftUI/Shape/rect
crawled: 2025-12-02T21:41:42Z
---

# rect

**Type Property**

A rectangular shape aligned inside the frame of the view containing it.

## Declaration

```swift
static var rect: Rectangle { get }
```

## Getting standard shapes

- **buttonBorder**: A shape that defers to the environment to determine the resolved button border shape.
- **capsule**: A capsule shape aligned inside the frame of the view containing it.
- **capsule(style:)**: A capsule shape aligned inside the frame of the view containing it.
- **circle**: A circle centered on the frame of the view containing it.
- **containerRelative**: A shape that is replaced by an inset version of the current container shape. If no container shape was defined, is replaced by a rectangle.
- **ellipse**: An ellipse aligned inside the frame of the view containing it.
- **rect(cornerRadii:style:)**: A rectangular shape with rounded corners with different values, aligned inside the frame of the view containing it.
- **rect(cornerRadius:style:)**: A rectangular shape with rounded corners, aligned inside the frame of the view containing it.
- **rect(cornerSize:style:)**: A rectangular shape with rounded corners, aligned inside the frame of the view containing it.
- **rect(topLeadingRadius:bottomLeadingRadius:bottomTrailingRadius:topTrailingRadius:style:)**: A rectangular shape with rounded corners with different values, aligned inside the frame of the view containing it.

