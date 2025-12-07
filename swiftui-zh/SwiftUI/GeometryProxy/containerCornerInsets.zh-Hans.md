--- 来源：https://developer.apple.com/documentation/SwiftUI/GeometryProxy/containerCornerInsets
抓取时间：2025-12-03T06:33:25Z

---

# containerCornerInsets

**实例属性**

返回容器视图的角内边距。使用此值可以根据容器视图重叠的角内边距调整视图的几何形状。角内边距可能包含系统 UI 的元素，以及窗口和演示文稿的圆角半径。

## 声明

```swift
var containerCornerInsets: RectangleCornerInsets { get }
```

## 讨论

```swift
GeometryReader { geometry in
    NavigationTitleView()
        .offset(x: geometry.containerCornerInsets.topLeading.width)
}
```

容器的角内边距大小可能不均匀。例如，在 iPadOS 和 macOS 上，当窗口填充整个屏幕但不显示窗口控件时，边距大小始终为零。当该窗口显示窗口控件，且视图与窗口控件区域重叠时，顶部前角的内嵌尺寸将等于重叠区域的大小。


---
source: https://developer.apple.com/documentation/SwiftUI/GeometryProxy/containerCornerInsets
crawled: 2025-12-03T06:33:25Z
---

# containerCornerInsets

**Instance Property**

Returns the corner insets of the container view. Use this value to adjust the geometry of a view based on the overlapping corner insets of the container view. Corner insets may include pieces of system UI as well as the corner radii for windows and presentations.

## Declaration

```swift
var containerCornerInsets: RectangleCornerInsets { get }
```

## Discussion

```swift
GeometryReader { geometry in
    NavigationTitleView()
        .offset(x: geometry.containerCornerInsets.topLeading.width)
}
```

Container corner inset sizes may not be uniform. For example, on iPadOS and macOS, when the window fills the entire screen without displaying window controls, the inset sizes will always be zero. When that window does display window controls, and the view overlaps the window control area, the corner inset size for the top leading corner will be the size of the overlapping area.

