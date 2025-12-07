---
来源： https://developer.apple.com/documentation/swiftui/scrolltransitionphase
抓取时间： 2025-12-04T13:37:22Z
---

# 滚动转换阶段

**Enumeration**

视图在其他视图间滚动时的转换阶段。

## 声明

```swift
@frozen enum ScrollTransitionPhase
```

## 概览

当应用了滚动转换修饰符的视图接近包含滚动视图或其他容器的可见区域时，首先会应用`topLeading` 或`bottomTrailing` 阶段（取决于视图接近的边缘）的效果，然后当视图移动到可见区域时，会移动到`identity` 阶段。决定视图何时在容器内可见的时间和行为由提供给`scrollTransition`修饰符的配置控制。

在`identity`阶段，滚动转换一般不会对所应用的视图产生任何视觉变化，因为只要视图可见，`identity`阶段的视图修改就会应用于该视图。在`topLeading` 和`bottomTrailing` 阶段，转场应应用将以动画方式创建转场的更改。

## 获取阶段

- **ScrollTransitionPhase.identity**：滚动转换正应用于可见区域内的视图。
- **ScrollTransitionPhase.topLeading**：在垂直滚动视图的上边缘或水平滚动视图的前边缘，滚动转换正应用于即将移动到可见区域的视图。
- **ScrollTransitionPhase.bottomTrailing**：滚动转换正应用于即将移动到垂直滚动视图底部边缘的可见区域或水平滚动视图尾部边缘的视图。

## 访问阶段状态

- **isIdentity**
- **value**：相位衍生值，可用于缩放或以其他方式修改效果。

## 滚动过渡动画

- **scrollTransition(_:axis:transition:)**：应用给定的过渡效果，当该视图在包含滚动视图的可视区域内出现和消失时，在过渡效果的各个阶段之间播放动画。
- **scrollTransition(topLeading:bottomTrailing:axis:transition:)**：应用给定的过渡，当该视图在包含滚动视图的可见区域内出现和消失时，在过渡的各个阶段之间播放动画。
- **ScrollTransitionConfiguration**：滚动过渡的配置，用于控制视图在包含滚动视图或其他容器的可见区域中滚动时如何应用过渡。

## 符合

- 比特可复制
- 可复制
- 等价
- 散列


---
source: https://developer.apple.com/documentation/swiftui/scrolltransitionphase
crawled: 2025-12-04T13:37:22Z
---

# ScrollTransitionPhase

**Enumeration**

The phases that a view transitions between when it scrolls among other views.

## Declaration

```swift
@frozen enum ScrollTransitionPhase
```

## Overview

When a view with a scroll transition modifier applied is approaching the visible region of the containing scroll view or other container, the effect  will first be applied with the `topLeading` or `bottomTrailing` phase (depending on which edge the view is approaching), then will be moved to the `identity` phase as the view moves into the visible area. The timing and behavior that determines when a view is visible within the container is controlled by the configuration that is provided to the `scrollTransition` modifier.

In the `identity` phase, scroll transitions should generally not make any visual change to the view they are applied to, since the transition’s view modifications in the `identity` phase will be applied to the view as long as it is visible. In the `topLeading` and `bottomTrailing` phases, transitions should apply a change that will be animated to create the transition.

## Getting the phase

- **ScrollTransitionPhase.identity**: The scroll transition is being applied to a view that is in the visible area.
- **ScrollTransitionPhase.topLeading**: The scroll transition is being applied to a view that is about to move into the visible area at the top edge of a vertical scroll view, or the leading edge of a horizont scroll view.
- **ScrollTransitionPhase.bottomTrailing**: The scroll transition is being applied to a view that is about to move into the visible area at the bottom edge of a vertical scroll view, or the trailing edge of a horizontal scroll view.

## Accessing the phase state

- **isIdentity**
- **value**: A phase-derived value that can be used to scale or otherwise modify effects.

## Animating scroll transitions

- **scrollTransition(_:axis:transition:)**: Applies the given transition, animating between the phases of the transition as this view appears and disappears within the visible region of the containing scroll view.
- **scrollTransition(topLeading:bottomTrailing:axis:transition:)**: Applies the given transition, animating between the phases of the transition as this view appears and disappears within the visible region of the containing scroll view.
- **ScrollTransitionConfiguration**: The configuration of a scroll transition that controls how a transition is applied as a view is scrolled through the visible region of a containing scroll view or other container.

## Conforms To

- BitwiseCopyable
- Copyable
- Equatable
- Hashable

