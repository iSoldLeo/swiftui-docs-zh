--- 来源：https://developer.apple.com/documentation/SwiftUI/ScaleTransition
抓取时间：2025-12-03T06:16:31Z

---

# ScaleTransition

**Structure**

返回一个缩放视图的过渡效果。

## 声明

```swift
struct ScaleTransition
```

## 创建过渡效果

- **init(_:anchor:)**：创建一个按指定比例缩放视图的过渡效果。

- **anchor**：缩放视图的锚点。

- **scale**：视图的缩放比例。

## 支持的类型

- **BlurReplaceTransition**：一个结合模糊和缩放效果，为视图的插入或移除添加动画效果的过渡效果。

- **IdentityTransition**：返回输入视图（未修改）作为输出视图的过渡效果。

- **MoveTransition**：返回一个将视图向指定边缘移动的过渡效果。

- **OffsetTransition**：返回一个将视图偏移指定距离的过渡效果。

- **OpacityTransition**：插入时从透明变为不透明，移除时从不透明变为透明的过渡效果。

- **PushTransition**：添加到视图后，插入视图时，从指定边缘向内移动并淡入；移除视图时，向相反边缘向外移动并淡出。

- **SlideTransition**：插入时从前缘向内移动，移除时向后缘向外移动。

## 符合

- 过渡


---
source: https://developer.apple.com/documentation/SwiftUI/ScaleTransition
crawled: 2025-12-03T06:16:31Z
---

# ScaleTransition

**Structure**

Returns a transition that scales the view.

## Declaration

```swift
struct ScaleTransition
```

## Creating the transition

- **init(_:anchor:)**: Creates a transition that scales the view by the specified amount.
- **anchor**: The anchor point to scale the view around.
- **scale**: The amount to scale the view by.

## Supporting types

- **BlurReplaceTransition**: A transition that animates the insertion or removal of a view by combining blurring and scaling effects.
- **IdentityTransition**: A transition that returns the input view, unmodified, as the output view.
- **MoveTransition**: Returns a transition that moves the view away, towards the specified edge of the view.
- **OffsetTransition**: Returns a transition that offset the view by the specified amount.
- **OpacityTransition**: A transition from transparent to opaque on insertion, and from opaque to transparent on removal.
- **PushTransition**: A transition that when added to a view will animate the view’s insertion by moving it in from the specified edge while fading it in, and animate its removal by moving it out towards the opposite edge and fading it out.
- **SlideTransition**: A transition that inserts by moving in from the leading edge, and removes by moving out towards the trailing edge.

## Conforms To

- Transition

