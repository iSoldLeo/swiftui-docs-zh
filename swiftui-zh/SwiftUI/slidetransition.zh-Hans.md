--- 来源：https://developer.apple.com/documentation/swiftui/slidetransition
抓取时间：2025-12-05T22:21:37Z

---

# SlideTransition

**Structure**

一种过渡效果，插入时从前缘向内移动，移除时向后缘向外移动。

## 声明

```swift
struct SlideTransition
```

## 概述

## 创建过渡效果

- **init()**

## 支持的类型

- **BlurReplaceTransition**：一种过渡效果，通过结合模糊和缩放效果来动画化视图的插入或移除。

- **IdentityTransition**：一种过渡效果，将输入视图原封不动地返回为输出视图。

- **MoveTransition**：返回一个将视图向指定边缘移动的过渡效果。

- **OffsetTransition**：返回一个将视图偏移指定数值的过渡效果。

- **OpacityTransition**：插入时从透明变为不透明，移除时从不透明变为透明的过渡效果。

- **PushTransition**：添加到视图后，视图插入时会从指定边缘向内移动并淡入，移除时会向相反边缘向外移动并淡出。

- **ScaleTransition**：返回一个缩放视图的过渡效果。

## 符合以下规范

- Transition


---
source: https://developer.apple.com/documentation/swiftui/slidetransition
crawled: 2025-12-05T22:21:37Z
---

# SlideTransition

**Structure**

A transition that inserts by moving in from the leading edge, and removes by moving out towards the trailing edge.

## Declaration

```swift
struct SlideTransition
```

## Overview



## Creating the transition

- **init()**

## Supporting types

- **BlurReplaceTransition**: A transition that animates the insertion or removal of a view by combining blurring and scaling effects.
- **IdentityTransition**: A transition that returns the input view, unmodified, as the output view.
- **MoveTransition**: Returns a transition that moves the view away, towards the specified edge of the view.
- **OffsetTransition**: Returns a transition that offset the view by the specified amount.
- **OpacityTransition**: A transition from transparent to opaque on insertion, and from opaque to transparent on removal.
- **PushTransition**: A transition that when added to a view will animate the view’s insertion by moving it in from the specified edge while fading it in, and animate its removal by moving it out towards the opposite edge and fading it out.
- **ScaleTransition**: Returns a transition that scales the view.

## Conforms To

- Transition

