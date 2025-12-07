---
来源： https://developer.apple.com/documentation/SwiftUI/MoveTransition
抓取时间： 2025-12-03T06:16:28Z
---

# 移动过渡

**Structure**

返回一个将视图移向指定视图边缘的过渡。

### 声明

```swift
struct MoveTransition
```

## 创建过渡

- **init(edge:)**：创建一个过渡，将视图移向指定的视图边缘。
- **edge**：要将视图移向的边缘。

## 支持类型

- **BlurReplaceTransition**：结合模糊和缩放效果，以动画方式插入或移除视图的过渡。
- **IdentityTransition**：将未修改的输入视图作为输出视图返回的变换。
- **OffsetTransition**：返回一个将视图偏移指定量的变换。
- **OpacityTransition**：插入时从透明到不透明，移除时从不透明到透明的过渡。
- **PushTransition**：添加到视图中的过渡，在插入视图时，会将视图从指定的边缘移入，同时使其渐变；在移除视图时，会将视图移出，同时使其渐变。
- **ScaleTransition**：返回缩放视图的过渡效果。
- **SlideTransition**：通过从前缘移入来插入，并通过向后缘移出来移除的过渡。

## 符合

- 过渡


---
source: https://developer.apple.com/documentation/SwiftUI/MoveTransition
crawled: 2025-12-03T06:16:28Z
---

# MoveTransition

**Structure**

Returns a transition that moves the view away, towards the specified edge of the view.

## Declaration

```swift
struct MoveTransition
```

## Creating the transition

- **init(edge:)**: Creates a transition that moves the view away, towards the specified edge of the view.
- **edge**: The edge to move the view towards.

## Supporting types

- **BlurReplaceTransition**: A transition that animates the insertion or removal of a view by combining blurring and scaling effects.
- **IdentityTransition**: A transition that returns the input view, unmodified, as the output view.
- **OffsetTransition**: Returns a transition that offset the view by the specified amount.
- **OpacityTransition**: A transition from transparent to opaque on insertion, and from opaque to transparent on removal.
- **PushTransition**: A transition that when added to a view will animate the view’s insertion by moving it in from the specified edge while fading it in, and animate its removal by moving it out towards the opposite edge and fading it out.
- **ScaleTransition**: Returns a transition that scales the view.
- **SlideTransition**: A transition that inserts by moving in from the leading edge, and removes by moving out towards the trailing edge.

## Conforms To

- Transition

