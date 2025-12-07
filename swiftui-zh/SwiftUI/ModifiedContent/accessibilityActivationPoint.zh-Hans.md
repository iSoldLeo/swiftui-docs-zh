---
来源： https://developer.apple.com/documentation/SwiftUI/ModifiedContent/accessibilityActivationPoint(_:)
抓取时间： 2025-12-02T17:46:49Z
---

# accessibilityActivationPoint(_:)

**实例方法**

元素的激活点是辅助技术用来启动手势的位置。

## 声明

```swift
nonisolated func accessibilityActivationPoint(_ activationPoint: CGPoint) -> ModifiedContent<Content, Modifier>
```

## 讨论

使用此修改器可确保即使向 VoiceOver 显示元素的较大版本，小元素的激活点仍能保持准确。

如果没有提供激活点，激活点将从无障碍元素的后代之一或无障碍框架的中心得出。


---
source: https://developer.apple.com/documentation/SwiftUI/ModifiedContent/accessibilityActivationPoint(_:)
crawled: 2025-12-02T17:46:49Z
---

# accessibilityActivationPoint(_:)

**Instance Method**

The activation point for an element is the location assistive technologies use to initiate gestures.

## Declaration

```swift
nonisolated func accessibilityActivationPoint(_ activationPoint: CGPoint) -> ModifiedContent<Content, Modifier>
```

## Discussion

Use this modifier to ensure that the activation point for a small element remains accurate even if you present a larger version of the element to VoiceOver.

If an activation point is not provided, an activation point will be derrived from one of the accessibility elements decendents or from the center of the accessibility frame.

