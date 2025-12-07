---
来源：https://developer.apple.com/documentation/SwiftUI/Transaction/animation
抓取时间： 2025-12-03T06:17:19Z
---

# 动画

**实例属性**

与当前状态变化相关的动画（如果有）。

## 声明

```swift
var animation: Animation? { get set }
```

## 管理动画

- **disablesAnimations**：布尔值，表示视图是否应禁用动画。
- **addAnimationCompletion(criteria:_:)**：添加一个完成程序，以便在该事务创建的动画全部完成时运行。


---
source: https://developer.apple.com/documentation/SwiftUI/Transaction/animation
crawled: 2025-12-03T06:17:19Z
---

# animation

**Instance Property**

The animation, if any, associated with the current state change.

## Declaration

```swift
var animation: Animation? { get set }
```

## Managing animations

- **disablesAnimations**: A Boolean value that indicates whether views should disable animations.
- **addAnimationCompletion(criteria:_:)**: Adds a completion to run when the animations created with this transaction are all complete.

