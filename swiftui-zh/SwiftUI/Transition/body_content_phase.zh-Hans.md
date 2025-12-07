---
来源：https://developer.apple.com/documentation/SwiftUI/Transition/body(内容：阶段：)
抓取时间： 2025-12-01T11:05:34Z
---

# body(content:phase:)

**实例方法**

获取调用者的当前正文。

## 声明

```swift
@ViewBuilder @MainActor @preconcurrency func body(content: Self.Content, phase: TransitionPhase) -> Self.Body
```

## 讨论

`content`是视图的代理，该视图将应用`Self`所代表的修饰符。

## 创建自定义过渡

- **Body**：代表主体的视图类型。
- **Transition.Content**：传递给 `body()` 的内容视图类型。


---
source: https://developer.apple.com/documentation/SwiftUI/Transition/body(content:phase:)
crawled: 2025-12-01T11:05:34Z
---

# body(content:phase:)

**Instance Method**

Gets the current body of the caller.

## Declaration

```swift
@ViewBuilder @MainActor @preconcurrency func body(content: Self.Content, phase: TransitionPhase) -> Self.Body
```

## Discussion

`content` is a proxy for the view that will have the modifier represented by `Self` applied to it.

## Creating a custom transition

- **Body**: The type of view representing the body.
- **Transition.Content**: The content view type passed to `body()`.

