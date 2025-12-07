--- 来源：https://developer.apple.com/documentation/SwiftUI/ScrollIndicatorVisibility/never
抓取时间：2025-12-03T06:43:02Z

---

# never

**类型属性**

滚动指示器应该始终不可见。

## 声明

```swift
static var never: ScrollIndicatorVisibility { get }
```

## 讨论

此值的行为类似于 [hidden](hidden.zh-Hans.md)，但会覆盖选择保持其指示器可见的可滚动视图。使用此值时，请提供替代的滚动方法。典型的水平滑动操作可能无法使用，具体取决于当前输入设备。

## 获取可见性

- **automatic**：滚动指示器的可见性取决于接受可见性配置的组件的策略。

- **hidden**：隐藏滚动指示器。

- **visible**：显示滚动指示器。


---
source: https://developer.apple.com/documentation/SwiftUI/ScrollIndicatorVisibility/never
crawled: 2025-12-03T06:43:02Z
---

# never

**Type Property**

Scroll indicators should never be visible.

## Declaration

```swift
static var never: ScrollIndicatorVisibility { get }
```

## Discussion

This value behaves like [hidden](hidden.zh-Hans.md), but overrides scrollable views that choose to keep their indidicators visible. When using this value, provide an alternative method of scrolling. The typical horizontal swipe gesture might not be available, depending on the current input device.

## Getting visibilties

- **automatic**: Scroll indicator visibility depends on the policies of the component accepting the visibility configuration.
- **hidden**: Hide the scroll indicators.
- **visible**: Show the scroll indicators.

