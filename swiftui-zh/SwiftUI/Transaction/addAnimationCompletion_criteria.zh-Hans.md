---
来源：https://developer.apple.com/documentation/SwiftUI/Transaction/addAnimationCompletion(标准:_:)
抓取时间：2025-12-03T06:17:21Z
---

# addAnimationCompletion(criteria:_:)

**实例方法**

添加一个完成项，在此事务创建的动画全部完成时运行。

## 声明

```swift
mutating func addAnimationCompletion(criteria: AnimationCompletionCriteria = .logicallyComplete, _ completion: @escaping () -> Void)
```

## 讨论

完成回调总是会触发一次。如果`body` 中的更改没有创建动画，那么回调将在`body` 之后立即被调用。

## 管理动画

- **animation**：与当前状态变化相关的动画（如果有）。
- **disablesAnimations**：布尔值，表示视图是否应禁用动画。


---
source: https://developer.apple.com/documentation/SwiftUI/Transaction/addAnimationCompletion(criteria:_:)
crawled: 2025-12-03T06:17:21Z
---

# addAnimationCompletion(criteria:_:)

**Instance Method**

Adds a completion to run when the animations created with this transaction are all complete.

## Declaration

```swift
mutating func addAnimationCompletion(criteria: AnimationCompletionCriteria = .logicallyComplete, _ completion: @escaping () -> Void)
```

## Discussion

The completion callback will always be fired exactly one time. If no animations are created by the changes in `body`, then the callback will be called immediately after `body`.

## Managing animations

- **animation**: The animation, if any, associated with the current state change.
- **disablesAnimations**: A Boolean value that indicates whether views should disable animations.

