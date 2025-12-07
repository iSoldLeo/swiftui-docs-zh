---
来源： https://developer.apple.com/documentation/SwiftUI/TransitionPhase/didDisappear
抓取时间： 2025-12-03T06:16:41Z
---

# TransitionPhase.didDisappear

**Case**

转换正应用于一个已请求从视图层次结构中删除的视图。

## 声明

```swift
case didDisappear
```

## 讨论

在这一阶段，过渡效果应显示为实现消失过渡而制作的动画外观。

## 获取阶段

- **TransitionPhase.identity**：该过渡正在应用于视图层次结构中的一个视图。
- **TransitionPhase.willAppear**：转换正应用于即将插入视图层次结构的视图。


---
source: https://developer.apple.com/documentation/SwiftUI/TransitionPhase/didDisappear
crawled: 2025-12-03T06:16:41Z
---

# TransitionPhase.didDisappear

**Case**

The transition is being applied to a view that has been requested to be removed from the view hierarchy.

## Declaration

```swift
case didDisappear
```

## Discussion

In this phase, a transition should show the appearance that will be animated to make the disappearance transition.

## Getting the phase

- **TransitionPhase.identity**: The transition is being applied to a view that is in the view hierarchy.
- **TransitionPhase.willAppear**: The transition is being applied to a view that is about to be inserted into the view hierarchy.

