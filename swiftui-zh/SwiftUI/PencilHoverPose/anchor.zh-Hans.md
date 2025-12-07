--- 来源：https://developer.apple.com/documentation/SwiftUI/PencilHoverPose/anchor
抓取时间：2025-12-03T06:43:49Z

---

# 锚点

**实例属性**

Apple Pencil 悬停在视图边界上方区域的位置，以相对于该视图的归一化锚点表示。

## 声明

```swift
let anchor: UnitPoint
```

## 说明

您可以将此锚点直接传递给演示修饰符，例如 [popover(isPresented:attachmentAnchor:arrowEdge:content:)](../View/popover_isPresented_attachmentAnchor_arrowEdge_content.zh-Hans.md)，或者如果您需要绝对点，请使用 [location](location.zh-Hans.md) 属性。

## 获取悬停特征

- **location**：Apple Pencil 悬停在视图边界上方区域的位置，以该视图坐标空间中的一个点表示。 - **zDistance**：屏幕与悬停的 Apple Pencil 之间的标准化距离。


---
source: https://developer.apple.com/documentation/SwiftUI/PencilHoverPose/anchor
crawled: 2025-12-03T06:43:49Z
---

# anchor

**Instance Property**

The location of an Apple Pencil hovering in the area above the view’s bounds, expressed as a normalized anchor point relative to that view.

## Declaration

```swift
let anchor: UnitPoint
```

## Discussion

You can pass this anchor point directly to a presentation modifier like [popover(isPresented:attachmentAnchor:arrowEdge:content:)](../View/popover_isPresented_attachmentAnchor_arrowEdge_content.zh-Hans.md) or use the [location](location.zh-Hans.md) property if you require an absolute point instead.

## Getting the hover characteristics

- **location**: The location of an Apple Pencil hovering in the area above the view’s bounds, expressed as a point in that view’s coordinate space.
- **zDistance**: The normalized distance between the screen and a hovering Apple Pencil.

