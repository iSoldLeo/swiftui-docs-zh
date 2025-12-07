--- 来源：https://developer.apple.com/documentation/SwiftUI/ScrollPhase/tracking
抓取时间：2025-12-03T06:42:57Z

---

# ScrollPhase.tracking

**Case**

跟踪阶段：滚动视图正在跟踪用户潜在的滚动操作，但用户尚未开始滚动。

## 声明

```swift
case tracking
```

## 讨论

例如，在 iOS 系统中，用户可能会开始触摸滚动视图中的内容。在用户移动手指之前，滚动视图会一直跟踪手指。并非所有平台或滚动方式都会触发此阶段。

## 获取滚动手势状态

- **ScrollPhase.animating**：动画阶段：滚动视图正在向最终目标位置进行动画处理。

- **ScrollPhase.decelerating**：减速阶段，用户已停止与滚动视图交互，滚动视图正减速至最终目标位置。

- **ScrollPhase.idle**：空闲阶段，此时滚动视图未发生任何滚动操作。

- **ScrollPhase.interacting**：交互阶段，此时用户正在与滚动视图进行交互。


---
source: https://developer.apple.com/documentation/SwiftUI/ScrollPhase/tracking
crawled: 2025-12-03T06:42:57Z
---

# ScrollPhase.tracking

**Case**

The tracking phase where the scroll view is tracking a potential scroll by the user but the user hasn’t started a scroll.

## Declaration

```swift
case tracking
```

## Discussion

For example, on iOS, the user may start touching content inside of the scroll view. Until the user moves their finger the scroll view would be tracking the finger. Not all platforms or kinds of scroll may trigger this phase.

## Getting scroll gesture states

- **ScrollPhase.animating**: The animating phase where the scroll view is animating towards a final target.
- **ScrollPhase.decelerating**: The decelerating phase where the user use has stopped interacting with the scroll view and the scroll view is decelerating towards its final target.
- **ScrollPhase.idle**: The idle phase where no kind of scrolling is occurring.
- **ScrollPhase.interacting**: The interacting phase where the user is interacting with the scroll view.

