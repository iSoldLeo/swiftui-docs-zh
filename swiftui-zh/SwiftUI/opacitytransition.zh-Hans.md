---
来源： https://developer.apple.com/documentation/swiftui/opacitytransition
抓取时间： 2025-12-05T22:21:36Z
---

# 不透明度转换

**Structure**

插入时从透明到不透明的过渡，移除时从不透明到透明的过渡。

## 声明

```swift
struct OpacityTransition
```

## 创建过渡

- **init()**

## 支持类型

- **BlurReplaceTransition**：结合模糊和缩放效果，以动画方式插入或移除视图的过渡。
- **IdentityTransition**：将未修改的输入视图作为输出视图返回的变换。
- **MoveTransition**：返回将视图移向指定视图边缘的变换。
- **OffsetTransition**：返回一个将视图偏移指定量的变换。
- **PushTransition**：添加到视图中的过渡，将通过从指定边缘向内移动视图并使其渐变，从而使视图的插入成为动画，以及通过向相反边缘移动视图并使其渐变，从而使视图的移除成为动画。
- **ScaleTransition**：返回缩放视图的过渡效果。
- **SlideTransition**：通过从前缘移入来插入，并通过向后缘移出来移除的过渡。

## 符合

- 过渡


---
source: https://developer.apple.com/documentation/swiftui/opacitytransition
crawled: 2025-12-05T22:21:36Z
---

# OpacityTransition

**Structure**

A transition from transparent to opaque on insertion, and from opaque to transparent on removal.

## Declaration

```swift
struct OpacityTransition
```

## Creating the transition

- **init()**

## Supporting types

- **BlurReplaceTransition**: A transition that animates the insertion or removal of a view by combining blurring and scaling effects.
- **IdentityTransition**: A transition that returns the input view, unmodified, as the output view.
- **MoveTransition**: Returns a transition that moves the view away, towards the specified edge of the view.
- **OffsetTransition**: Returns a transition that offset the view by the specified amount.
- **PushTransition**: A transition that when added to a view will animate the view’s insertion by moving it in from the specified edge while fading it in, and animate its removal by moving it out towards the opposite edge and fading it out.
- **ScaleTransition**: Returns a transition that scales the view.
- **SlideTransition**: A transition that inserts by moving in from the leading edge, and removes by moving out towards the trailing edge.

## Conforms To

- Transition

