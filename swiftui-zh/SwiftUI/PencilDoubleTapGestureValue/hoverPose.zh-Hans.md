---
来源： https://developer.apple.com/documentation/SwiftUI/PencilDoubleTapGestureValue/hoverPose
抓取时间： 2025-12-03T06:43:45Z
---

# hoverPose

**实例属性**

当双击手势发生时，Apple Pencil 在视图边界上方区域悬停的位置和距离。

## 声明

```swift
let hoverPose: PencilHoverPose?
```

## 讨论

如果用户双击 Apple Pencil 时，Apple Pencil 正悬停在视图边界上方的区域，该属性就会描述它相对于视图的姿势。

相反，如果 Apple Pencil 没有悬停在视图边界上方的区域，或者设备无法检测到悬停的 Apple Pencil，则此属性为`nil`。


---
source: https://developer.apple.com/documentation/SwiftUI/PencilDoubleTapGestureValue/hoverPose
crawled: 2025-12-03T06:43:45Z
---

# hoverPose

**Instance Property**

The location and distance of an Apple Pencil hovering in the area above the view’s bounds when the double-tap gesture occurred.

## Declaration

```swift
let hoverPose: PencilHoverPose?
```

## Discussion

If the Apple Pencil was hovering in the area above the view’s bounds when the user double-tapped their Apple Pencil, this property describes its pose relative to that view.

Conversely, if the Apple Pencil wasn’t hovering in the area above the view’s bounds or if the device can’t detect a hovering Apple Pencil, this property is `nil`.

