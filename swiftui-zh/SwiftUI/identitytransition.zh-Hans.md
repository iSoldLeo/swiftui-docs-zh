--- 来源：https://developer.apple.com/documentation/swiftui/identitytransition
抓取时间：2025-12-05T22:21:35Z

---

# IdentityTransition

**Structure**

一种过渡效果，将输入视图原封不动地作为输出视图返回。

## 声明

```swift
struct IdentityTransition
```

## 创建过渡效果

- **init()**

## 支持的类型

- **BlurReplaceTransition**：一种过渡效果，通过结合模糊和缩放效果，为视图的插入或移除添加动画。

- **MoveTransition**：返回一种过渡效果，将视图向指定的视图边缘移动。

- **OffsetTransition**：返回一种过渡效果，将视图偏移指定的量。

- **OpacityTransition**：插入时从透明到不透明的过渡效果，移除时从不透明到透明的过渡效果。

- **PushTransition**：添加到视图后，视图插入时会从指定边缘向内移动并淡入，移除时会向相反边缘向外移动并淡出，从而实现动画效果。

- **ScaleTransition**：返回一个缩放视图的过渡效果。

- **SlideTransition**：插入时从前缘向内移动，移除时向后缘向外移动，从而实现动画效果。

## 符合以下规范

- Transition


---
source: https://developer.apple.com/documentation/swiftui/identitytransition
crawled: 2025-12-05T22:21:35Z
---

# IdentityTransition

**Structure**

A transition that returns the input view, unmodified, as the output view.

## Declaration

```swift
struct IdentityTransition
```

## Creating the transition

- **init()**

## Supporting types

- **BlurReplaceTransition**: A transition that animates the insertion or removal of a view by combining blurring and scaling effects.
- **MoveTransition**: Returns a transition that moves the view away, towards the specified edge of the view.
- **OffsetTransition**: Returns a transition that offset the view by the specified amount.
- **OpacityTransition**: A transition from transparent to opaque on insertion, and from opaque to transparent on removal.
- **PushTransition**: A transition that when added to a view will animate the view’s insertion by moving it in from the specified edge while fading it in, and animate its removal by moving it out towards the opposite edge and fading it out.
- **ScaleTransition**: Returns a transition that scales the view.
- **SlideTransition**: A transition that inserts by moving in from the leading edge, and removes by moving out towards the trailing edge.

## Conforms To

- Transition

