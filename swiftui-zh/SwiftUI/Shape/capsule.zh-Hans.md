---
来源： https://developer.apple.com/documentation/SwiftUI/Shape/capsule
抓取时间：2025-12-02T21:41:38Z
---

# 胶囊

**类型属性**

在视图框架内对齐的胶囊形状。

## 声明

```swift
static var capsule: Capsule { get }
```

## 讨论

胶囊形状相当于一个圆角矩形，其角半径选为矩形最小边长的一半。

## 获取标准形状

- **buttonBorder**：服从环境决定已解决按钮边框形状的形状。
- **capsule(style:)**：在包含它的视图框架内对齐的胶囊形状。
- **circle**：以包含它的视图框架为中心的圆。
- **containerRelative**：由当前容器形状的嵌入版本替换的形状。如果没有定义容器形状，则会被矩形替换。
- **ellipse**：在包含它的视图框架内对齐的椭圆。
- **rect**：在包含它的视图框架内对齐的矩形。
- **rect(cornerRadii:style:)**：在包含它的视图框架内对齐的矩形，带有不同值的圆角。
- **rect(cornerRadius:style:)**：带圆角的矩形，在包含它的视图框架内对齐。
- **rect(cornerSize:style:)**：带圆角的矩形，在包含它的视图的边框内对齐。
- **rect(topLeadingRadius:bottomLeadingRadius:bottomTrailingRadius:topTrailingRadius:style:)**：带有不同值的圆角矩形，在包含该矩形的视图框架内对齐。


---
source: https://developer.apple.com/documentation/SwiftUI/Shape/capsule
crawled: 2025-12-02T21:41:38Z
---

# capsule

**Type Property**

A capsule shape aligned inside the frame of the view containing it.

## Declaration

```swift
static var capsule: Capsule { get }
```

## Discussion

A capsule shape is equivalent to a rounded rectangle where the corner radius is chosen as half the length of the rectangle’s smallest edge.

## Getting standard shapes

- **buttonBorder**: A shape that defers to the environment to determine the resolved button border shape.
- **capsule(style:)**: A capsule shape aligned inside the frame of the view containing it.
- **circle**: A circle centered on the frame of the view containing it.
- **containerRelative**: A shape that is replaced by an inset version of the current container shape. If no container shape was defined, is replaced by a rectangle.
- **ellipse**: An ellipse aligned inside the frame of the view containing it.
- **rect**: A rectangular shape aligned inside the frame of the view containing it.
- **rect(cornerRadii:style:)**: A rectangular shape with rounded corners with different values, aligned inside the frame of the view containing it.
- **rect(cornerRadius:style:)**: A rectangular shape with rounded corners, aligned inside the frame of the view containing it.
- **rect(cornerSize:style:)**: A rectangular shape with rounded corners, aligned inside the frame of the view containing it.
- **rect(topLeadingRadius:bottomLeadingRadius:bottomTrailingRadius:topTrailingRadius:style:)**: A rectangular shape with rounded corners with different values, aligned inside the frame of the view containing it.

