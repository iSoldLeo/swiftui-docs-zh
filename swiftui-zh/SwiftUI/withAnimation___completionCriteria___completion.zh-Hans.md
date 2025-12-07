---
来源：https://developer.apple.com/documentation/SwiftUI/withAnimation(_:completionCriteria:_:completion:)
抓取时间： 2025-12-02T17:33:47Z
---

# withAnimation(_:completionCriteria:_:completion:)

**Function**

返回使用提供的动画重新计算视图主体的结果，并在所有动画完成后运行 completion。

### 声明

```swift
func withAnimation<Result>(_ animation: Animation? = .default, completionCriteria: AnimationCompletionCriteria = .logicallyComplete, _ body: () throws -> Result, completion: @escaping () -> Void) rethrows -> Result
```

## 讨论

此函数将给定的[Animation](Animation.zh-Hans.md) 设置为线程当前[animation](Transaction/animation.zh-Hans.md) 属性的[Transaction](Transaction.zh-Hans.md)，并以指定的完成度调用`Transaction/addAnimationCompletion`。

完成回调总是会准确地触发一次。如果`body` 中的更改没有创建动画，则回调将在`body` 之后立即调用。

## 为动作添加基于状态的动画

- **withAnimation(_:_:)**：返回使用所提供的动画重新计算视图主体的结果。
- **AnimationCompletionCriteria**：决定动画何时被视为完成的标准。
- **Animation**：视图随时间变化的方式，以创建从一种状态到另一种状态的平滑视觉过渡。


---
source: https://developer.apple.com/documentation/SwiftUI/withAnimation(_:completionCriteria:_:completion:)
crawled: 2025-12-02T17:33:47Z
---

# withAnimation(_:completionCriteria:_:completion:)

**Function**

Returns the result of recomputing the view’s body with the provided animation, and runs the completion when all animations are complete.

## Declaration

```swift
func withAnimation<Result>(_ animation: Animation? = .default, completionCriteria: AnimationCompletionCriteria = .logicallyComplete, _ body: () throws -> Result, completion: @escaping () -> Void) rethrows -> Result
```

## Discussion

This function sets the given [Animation](Animation.zh-Hans.md) as the [animation](Transaction/animation.zh-Hans.md) property of the thread’s current [Transaction](Transaction.zh-Hans.md) as well as calling `Transaction/addAnimationCompletion` with the specified completion.

The completion callback will always be fired exactly one time. If no animations are created by the changes in `body`, then the callback will be called immediately after `body`.

## Adding state-based animation to an action

- **withAnimation(_:_:)**: Returns the result of recomputing the view’s body with the provided animation.
- **AnimationCompletionCriteria**: The criteria that determines when an animation is considered finished.
- **Animation**: The way a view changes over time to create a smooth visual transition from one state to another.

