---
来源： https://developer.apple.com/documentation/SwiftUI/withAnimation(_:_:)
抓取时间： 2025-12-02T17:33:46Z
---

# withAnimation(_:_:)

**Function**

返回使用所提供的动画重新计算视图主体的结果。

## 声明

```swift
func withAnimation<Result>(_ animation: Animation? = .default, _ body: () throws -> Result) rethrows -> Result
```

## 讨论

此函数将给定的[Animation](Animation.zh-Hans.md) 设置为线程当前[animation](Transaction/animation.zh-Hans.md) 属性。

## 为动作添加基于状态的动画

- **withAnimation(_:completionCriteria:_:completion:)**：返回用提供的动画重新计算视图主体的结果，并在所有动画完成后运行完成。
- **AnimationCompletionCriteria**：决定动画何时被视为完成的标准。
- **Animation**：视图随时间变化的方式，以创建从一种状态到另一种状态的平滑视觉过渡。


---
source: https://developer.apple.com/documentation/SwiftUI/withAnimation(_:_:)
crawled: 2025-12-02T17:33:46Z
---

# withAnimation(_:_:)

**Function**

Returns the result of recomputing the view’s body with the provided animation.

## Declaration

```swift
func withAnimation<Result>(_ animation: Animation? = .default, _ body: () throws -> Result) rethrows -> Result
```

## Discussion

This function sets the given [Animation](Animation.zh-Hans.md) as the [animation](Transaction/animation.zh-Hans.md) property of the thread’s current [Transaction](Transaction.zh-Hans.md).

## Adding state-based animation to an action

- **withAnimation(_:completionCriteria:_:completion:)**: Returns the result of recomputing the view’s body with the provided animation, and runs the completion when all animations are complete.
- **AnimationCompletionCriteria**: The criteria that determines when an animation is considered finished.
- **Animation**: The way a view changes over time to create a smooth visual transition from one state to another.

