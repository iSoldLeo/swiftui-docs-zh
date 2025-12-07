---
来源： https://developer.apple.com/documentation/SwiftUI/AnimationCompletionCriteria
抓取时间： 2025-12-02T17:33:47Z
---

# 动画完成标准

**Structure**

决定动画何时被视为完成的标准。

## 声明

```swift
struct AnimationCompletionCriteria
```

## 获取完成标准

- **logicallyComplete**：动画在逻辑上已完成，但可能仍处于长尾阶段。
- **removed**：整个动画已经完成，现在将被删除。

## 为动作添加基于状态的动画

- **withAnimation(_:_:)**：返回使用所提供的动画重新计算视图主体的结果。
- **withAnimation(_:completionCriteria:_:completion:)**：返回用提供的动画重新计算视图主体的结果，并在所有动画完成后运行完成。
- **Animation**：视图随时间变化的方式，用于创建从一种状态到另一种状态的平滑视觉过渡。

## 符合

- 等价
- 可散列
- 可发送
- 可发送元类型


---
source: https://developer.apple.com/documentation/SwiftUI/AnimationCompletionCriteria
crawled: 2025-12-02T17:33:47Z
---

# AnimationCompletionCriteria

**Structure**

The criteria that determines when an animation is considered finished.

## Declaration

```swift
struct AnimationCompletionCriteria
```

## Getting the completion criteria

- **logicallyComplete**: The animation has logically completed, but may still be in its long tail.
- **removed**: The entire animation is finished and will now be removed.

## Adding state-based animation to an action

- **withAnimation(_:_:)**: Returns the result of recomputing the view’s body with the provided animation.
- **withAnimation(_:completionCriteria:_:completion:)**: Returns the result of recomputing the view’s body with the provided animation, and runs the completion when all animations are complete.
- **Animation**: The way a view changes over time to create a smooth visual transition from one state to another.

## Conforms To

- Equatable
- Hashable
- Sendable
- SendableMetatype

