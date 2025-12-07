--- 来源：https://developer.apple.com/documentation/SwiftUI/ScrollPhase/animating
抓取时间：2025-12-03T06:42:54Z

---

# ScrollPhase.animating

**Case**

滚动视图向最终目标滚动的动画阶段。

## 声明

```swift
case animating
```

## 讨论

当使用 [ScrollViewReader](../ScrollViewReader.zh-Hans.md) 或 [scrollPosition(id:anchor:)](../View/scrollPosition_id_anchor.zh-Hans.md) 修饰符进行程序化滚动时，此阶段是结果。

当使用 [onScrollPhaseChange(_:)](../View/onScrollPhaseChange.zh-Hans.md) 修饰符以及 [ScrollView](../ScrollView.zh-Hans.md) 或 [List](../List.zh-Hans.md) 等可滚动视图时，SwiftUI 会提供此类型的值。

## 获取滚动手势状态

- **ScrollPhase.decelerating**：减速阶段，用户已停止与滚动视图交互，滚动视图正在减速至最终目标位置。

- **ScrollPhase.idle**：空闲阶段，此时没有任何滚动操作。

- **ScrollPhase.interacting**：交互阶段，用户正在与滚动视图交互。

- **ScrollPhase.tracking**：跟踪阶段，滚动视图正在跟踪用户的潜在滚动操作，但用户尚未开始滚动。


---
source: https://developer.apple.com/documentation/SwiftUI/ScrollPhase/animating
crawled: 2025-12-03T06:42:54Z
---

# ScrollPhase.animating

**Case**

The animating phase where the scroll view is animating towards a final target.

## Declaration

```swift
case animating
```

## Discussion

This phase is the result of a programmatic scroll when using a [ScrollViewReader](../ScrollViewReader.zh-Hans.md) or [scrollPosition(id:anchor:)](../View/scrollPosition_id_anchor.zh-Hans.md) modifier.

SwiftUI provides you a value of this type when using the [onScrollPhaseChange(_:)](../View/onScrollPhaseChange.zh-Hans.md) modifier with a scrollable view like [ScrollView](../ScrollView.zh-Hans.md) or [List](../List.zh-Hans.md).

## Getting scroll gesture states

- **ScrollPhase.decelerating**: The decelerating phase where the user use has stopped interacting with the scroll view and the scroll view is decelerating towards its final target.
- **ScrollPhase.idle**: The idle phase where no kind of scrolling is occurring.
- **ScrollPhase.interacting**: The interacting phase where the user is interacting with the scroll view.
- **ScrollPhase.tracking**: The tracking phase where the scroll view is tracking a potential scroll by the user but the user hasn’t started a scroll.

