--- 来源：https://developer.apple.com/documentation/SwiftUI/PencilHoverPose/location
抓取时间：2025-12-03T06:43:50Z

---

# location

**实例属性**

Apple Pencil 悬停在视图边界上方区域时的位置，以该视图坐标空间中的一个点表示。

## 声明

```swift
let location: CGPoint
```

## 说明

如果您需要一个归一化的锚点来配合显示修饰符使用，请使用 [anchor](anchor.zh-Hans.md) 属性。

## 获取悬停特征

- **anchor**：Apple Pencil 悬停在视图边界上方区域时的位置，以相对于该视图的归一化锚点表示。

- **zDistance**：屏幕与悬停的 Apple Pencil 之间的标准化距离。


---
source: https://developer.apple.com/documentation/SwiftUI/PencilHoverPose/location
crawled: 2025-12-03T06:43:50Z
---

# location

**Instance Property**

The location of an Apple Pencil hovering in the area above the view’s bounds, expressed as a point in that view’s coordinate space.

## Declaration

```swift
let location: CGPoint
```

## Discussion

Use the [anchor](anchor.zh-Hans.md) property if you require a normalized anchor point for use with a presentation modifier instead.

## Getting the hover characteristics

- **anchor**: The location of an Apple Pencil hovering in the area above the view’s bounds, expressed as a normalized anchor point relative to that view.
- **zDistance**: The normalized distance between the screen and a hovering Apple Pencil.

