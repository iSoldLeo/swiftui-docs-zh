---
来源： https://developer.apple.com/documentation/SwiftUI/ModifiedContent/accessibilityActivationPoint(_:isEnabled:)
抓取时间： 2025-12-02T17:46:50Z
---

# accessibilityActivationPoint(_:isEnabled:)

**实例方法**

元素的激活点是辅助技术用来启动手势的位置。

## 声明

```swift
nonisolated func accessibilityActivationPoint(_ activationPoint: CGPoint, isEnabled: Bool) -> ModifiedContent<Content, Modifier>
```

## 参数

- **activationPoint**：要应用的无障碍激活点。
- **isEnabled**：如果为 true，则应用无障碍激活点；否则，无障碍激活点保持不变。

## 讨论

使用此修改器可确保即使向 VoiceOver 显示较大版本的元素，小元素的激活点仍能保持准确。

如果没有提供激活点，激活点将从其中一个无障碍元素的后缀或无障碍框架的中心导出。


---
source: https://developer.apple.com/documentation/SwiftUI/ModifiedContent/accessibilityActivationPoint(_:isEnabled:)
crawled: 2025-12-02T17:46:50Z
---

# accessibilityActivationPoint(_:isEnabled:)

**Instance Method**

The activation point for an element is the location assistive technologies use to initiate gestures.

## Declaration

```swift
nonisolated func accessibilityActivationPoint(_ activationPoint: CGPoint, isEnabled: Bool) -> ModifiedContent<Content, Modifier>
```

## Parameters

- **activationPoint**: The accessibility activation point to apply.
- **isEnabled**: If true the accessibility activation point is applied; otherwise the accessibility activation point is unchanged.

## Discussion

Use this modifier to ensure that the activation point for a small element remains accurate even if you present a larger version of the element to VoiceOver.

If an activation point is not provided, an activation point will be derived from one of the accessibility elements decedents or from the center of the accessibility frame.

