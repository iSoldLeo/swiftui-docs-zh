---
来源： https://developer.apple.com/documentation/SwiftUI/TransitionPhase/identity
抓取时间： 2025-12-03T06:16:39Z
---

# TransitionPhase.identity

**Case**

转换正应用于视图层次结构中的视图。

## 声明

```swift
case identity
```

## 讨论

在这一阶段，过渡应显示其稳定状态外观，一般不会对视图产生任何视觉变化。

## 获取阶段

- **TransitionPhase.willAppear**：转换正在应用于即将插入视图层次结构的视图。
- **TransitionPhase.didDisappear**：该转换正应用于已请求从视图层次结构中删除的视图。


---
source: https://developer.apple.com/documentation/SwiftUI/TransitionPhase/identity
crawled: 2025-12-03T06:16:39Z
---

# TransitionPhase.identity

**Case**

The transition is being applied to a view that is in the view hierarchy.

## Declaration

```swift
case identity
```

## Discussion

In this phase, a transition should show its steady state appearance, which will generally not make any visual change to the view.

## Getting the phase

- **TransitionPhase.willAppear**: The transition is being applied to a view that is about to be inserted into the view hierarchy.
- **TransitionPhase.didDisappear**: The transition is being applied to a view that has been requested to be removed from the view hierarchy.

