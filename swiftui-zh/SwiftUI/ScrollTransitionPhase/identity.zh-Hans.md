---
来源： https://developer.apple.com/documentation/SwiftUI/ScrollTransitionPhase/identity
抓取时间： 2025-12-03T06:42:35Z
---

# ScrollTransitionPhase.identity

**Case**

滚动转换正应用于可见区域中的视图。

## 声明

```swift
case identity
```

## 讨论

在这一阶段，过渡应显示其稳定状态外观，一般不会对视图产生任何视觉变化。

## 获取阶段

- **ScrollTransitionPhase.topLeading**：滚动转换正应用于即将移动到垂直滚动视图顶端边缘或水平滚动视图前端边缘可见区域的视图。
- **ScrollTransitionPhase.bottomTrailing**：滚动转换正应用于即将移动到垂直滚动视图底部边缘的可见区域或水平滚动视图尾部边缘的视图。


---
source: https://developer.apple.com/documentation/SwiftUI/ScrollTransitionPhase/identity
crawled: 2025-12-03T06:42:35Z
---

# ScrollTransitionPhase.identity

**Case**

The scroll transition is being applied to a view that is in the visible area.

## Declaration

```swift
case identity
```

## Discussion

In this phase, a transition should show its steady state appearance, which will generally not make any visual change to the view.

## Getting the phase

- **ScrollTransitionPhase.topLeading**: The scroll transition is being applied to a view that is about to move into the visible area at the top edge of a vertical scroll view, or the leading edge of a horizont scroll view.
- **ScrollTransitionPhase.bottomTrailing**: The scroll transition is being applied to a view that is about to move into the visible area at the bottom edge of a vertical scroll view, or the trailing edge of a horizontal scroll view.

