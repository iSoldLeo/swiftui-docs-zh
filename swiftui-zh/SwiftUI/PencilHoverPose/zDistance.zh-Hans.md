--- 来源：https://developer.apple.com/documentation/SwiftUI/PencilHoverPose/zDistance
抓取时间：2025-12-03T06:43:51Z

---

# zDistance

**实例属性**

屏幕与悬停的 Apple Pencil 之间的归一化距离。

## 声明

```swift
let zDistance: CGFloat
```

## 说明

当 Apple Pencil 距离屏幕最远时，该值为 `1`，随着 Apple Pencil 靠近屏幕，该值逐渐接近 `0`。

## 获取悬停特性

- **anchor**：Apple Pencil 在视图边界上方区域悬停时的位置，以相对于该视图的归一化锚点表示。

- **location**：Apple Pencil 悬停在视图边界上方区域时的位置，以该视图坐标空间中的一个点表示。


---
source: https://developer.apple.com/documentation/SwiftUI/PencilHoverPose/zDistance
crawled: 2025-12-03T06:43:51Z
---

# zDistance

**Instance Property**

The normalized distance between the screen and a hovering Apple Pencil.

## Declaration

```swift
let zDistance: CGFloat
```

## Discussion

This value is `1` at the maximum distance from the screen and approaches `0` as the Apple Pencil gets closer to the screen.

## Getting the hover characteristics

- **anchor**: The location of an Apple Pencil hovering in the area above the view’s bounds, expressed as a normalized anchor point relative to that view.
- **location**: The location of an Apple Pencil hovering in the area above the view’s bounds, expressed as a point in that view’s coordinate space.

