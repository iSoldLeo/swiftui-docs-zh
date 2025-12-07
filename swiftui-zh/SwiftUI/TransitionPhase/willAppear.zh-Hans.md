---
来源： https://developer.apple.com/documentation/SwiftUI/TransitionPhase/willAppear
抓取时间： 2025-12-03T06:16:40Z
---

# TransitionPhase.willAppear

**Case**

转换正应用于即将插入视图层次结构的视图。

## 声明

```swift
case willAppear
```

## 讨论

在这一阶段，过渡应显示将从哪个外观进行动画，以实现外观过渡。

## 获取阶段

- **TransitionPhase.identity**：正在将该过渡应用于视图层次结构中的一个视图。
- **TransitionPhase.didDisappear**：正在对已请求从视图层次结构中删除的视图应用转换。


---
source: https://developer.apple.com/documentation/SwiftUI/TransitionPhase/willAppear
crawled: 2025-12-03T06:16:40Z
---

# TransitionPhase.willAppear

**Case**

The transition is being applied to a view that is about to be inserted into the view hierarchy.

## Declaration

```swift
case willAppear
```

## Discussion

In this phase, a transition should show the appearance that will be animated from to make the appearance transition.

## Getting the phase

- **TransitionPhase.identity**: The transition is being applied to a view that is in the view hierarchy.
- **TransitionPhase.didDisappear**: The transition is being applied to a view that has been requested to be removed from the view hierarchy.

