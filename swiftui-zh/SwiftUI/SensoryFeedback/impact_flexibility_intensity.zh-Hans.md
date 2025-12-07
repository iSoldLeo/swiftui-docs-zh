---
来源：https://developer.apple.com/documentation/SwiftUI/SensoryFeedback/impact(灵活性:强度:)
抓取时间： 2025-12-01T11:11:20Z
---

# impact(flexibility:intensity:)

**类型方法**

提供一种物理隐喻，用于补充视觉体验。

## 声明

```swift
static func impact(flexibility: SensoryFeedback.Flexibility, intensity: Double = 1.0) -> SensoryFeedback
```

## 讨论

使用此功能可为用户界面元素碰撞提供反馈。由于只有某些平台才会播放反馈，因此它应作为用户体验的补充。

并非所有平台都会针对不同的灵活性和碰撞强度播放不同的反馈。

仅在 iOS 和 watchOS 上播放反馈。

## 产生物理冲击

- **impact**：提供物理隐喻，用于补充视觉体验。
- **impact(weight:intensity:)**：提供了一个物理隐喻，可以用来补充视觉体验。
- **SensoryFeedback.Flexibility**：反馈类型所代表的灵活性。
- **SensoryFeedback.Weight**：反馈类型所代表的权重。


---
source: https://developer.apple.com/documentation/SwiftUI/SensoryFeedback/impact(flexibility:intensity:)
crawled: 2025-12-01T11:11:20Z
---

# impact(flexibility:intensity:)

**Type Method**

Provides a physical metaphor you can use to complement a visual experience.

## Declaration

```swift
static func impact(flexibility: SensoryFeedback.Flexibility, intensity: Double = 1.0) -> SensoryFeedback
```

## Discussion

Use this to provide feedback for UI elements colliding. It should supplement the user experience, since only some platforms will play feedback in response to it.

Not all platforms will play different feedback for different flexibilities and intensities of impact.

Only plays feedback on iOS and watchOS.

## Producing a physical impact

- **impact**: Provides a physical metaphor you can use to complement a visual experience.
- **impact(weight:intensity:)**: Provides a physical metaphor you can use to complement a visual experience.
- **SensoryFeedback.Flexibility**: The flexibility to be represented by a type of feedback.
- **SensoryFeedback.Weight**: The weight to be represented by a type of feedback.

