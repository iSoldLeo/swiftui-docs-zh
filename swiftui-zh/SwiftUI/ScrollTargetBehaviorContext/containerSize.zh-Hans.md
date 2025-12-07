--- 来源：https://developer.apple.com/documentation/SwiftUI/ScrollTargetBehaviorContext/containerSize

抓取时间：2025-12-03T06:42:18Z

---

# containerSize

**实例属性**

可滚动视图容器的大小。

## 声明

```swift
var containerSize: CGSize { get }
```

## 说明

这是滚动视图边界的大小，减去应用于滚动视图的任何内边距（例如安全区域）。

## 获取滚动目标行为上下文

- **axes**：可滚动视图可滚动的轴。

- **contentSize**：可滚动视图内容的大小。

- **originalTarget**：滚动手势开始时的原始目标。

- **velocity**：可滚动视图当前滚动速度。


---
source: https://developer.apple.com/documentation/SwiftUI/ScrollTargetBehaviorContext/containerSize
crawled: 2025-12-03T06:42:18Z
---

# containerSize

**Instance Property**

The size of the container of the scrollable view.

## Declaration

```swift
var containerSize: CGSize { get }
```

## Discussion

This is the size of the bounds of the scroll view subtracting any insets applied to the scroll view (like the safe area).

## Getting the scroll target behavior context

- **axes**: The axes in which the scrollable view is scrollable.
- **contentSize**: The size of the content of the scrollable view.
- **originalTarget**: The original target when the scroll gesture began.
- **velocity**: The current velocity of the scrollable view’s scroll gesture.

