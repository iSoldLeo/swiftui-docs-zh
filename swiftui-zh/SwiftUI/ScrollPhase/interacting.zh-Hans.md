--- 来源：https://developer.apple.com/documentation/SwiftUI/ScrollPhase/interacting
抓取时间：2025-12-03T06:42:56Z

---

# ScrollPhase.interacting

**Case**

交互阶段，用户正在与滚动视图进行交互。

## 声明

```swift
case interacting
```

## 获取滚动手势状态

- **ScrollPhase.animating**：动画阶段，滚动视图正在向最终目标位置滚动。

- **ScrollPhase.decelerating**：减速阶段，用户已停止与滚动视图交互，滚动视图正在减速向最终目标位置滚动。

- **ScrollPhase.idle**：空闲阶段，此时没有任何滚动操作。

- **ScrollPhase.tracking**：跟踪阶段，滚动视图正在跟踪用户潜在的滚动操作，但用户尚未开始滚动。


---
source: https://developer.apple.com/documentation/SwiftUI/ScrollPhase/interacting
crawled: 2025-12-03T06:42:56Z
---

# ScrollPhase.interacting

**Case**

The interacting phase where the user is interacting with the scroll view.

## Declaration

```swift
case interacting
```

## Getting scroll gesture states

- **ScrollPhase.animating**: The animating phase where the scroll view is animating towards a final target.
- **ScrollPhase.decelerating**: The decelerating phase where the user use has stopped interacting with the scroll view and the scroll view is decelerating towards its final target.
- **ScrollPhase.idle**: The idle phase where no kind of scrolling is occurring.
- **ScrollPhase.tracking**: The tracking phase where the scroll view is tracking a potential scroll by the user but the user hasn’t started a scroll.

