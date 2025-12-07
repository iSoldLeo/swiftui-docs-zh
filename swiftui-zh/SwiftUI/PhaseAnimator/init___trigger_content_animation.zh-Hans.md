---
来源：https://developer.apple.com/documentation/SwiftUI/PhaseAnimator/init(_:触发器:内容:动画:)
抓取时间：2025-12-02T20:59:18Z
---

# init(_:trigger:content:animation:)

**Initializer**

根据指定值的变化循环播放一系列阶段，在每个阶段变化时对视图进行动画更新。

### 声明

```swift
init(_ phases: some Sequence<Phase>, trigger: some Equatable, @ViewBuilder content: @escaping (Phase) -> Content, animation: @escaping (Phase) -> Animation? = { _ in .default })
```

## 参数

- **phases**：要循环播放的阶段序列。确保序列不是空的。如果为空，SwiftUI 将记录运行时警告，并返回可视警告作为输出视图。
- **trigger**：一个值，该值的变化会导致动画播放器使用下一阶段。
- **content**：视图生成器闭包，将当前阶段作为输入。返回一个基于阶段输入的视图。
- **animation**：以当前阶段作为输入的闭包。返回过渡到下一阶段时使用的动画。如果返回 `nil`，则过渡不会产生动画。如果不设置此参数，SwiftUI 将使用默认动画。

## 讨论

当相位动画器首次出现时，该初始化程序会使用第一个相位作为闭包的输入来渲染`content` 闭包。当`trigger` 输入的值发生变化时，动画器会使用第二阶段的值重新评估`content` 闭包，并对变化进行动画处理。这一过程在每个连续阶段重复进行，直到最后一个阶段，此时动画播放器会循环回到第一阶段。

## 创建阶段动画

- **init(_:content:animation:)**：在一连串的阶段中不断循环，在每个阶段变化时对视图进行动画更新。


---
source: https://developer.apple.com/documentation/SwiftUI/PhaseAnimator/init(_:trigger:content:animation:)
crawled: 2025-12-02T20:59:18Z
---

# init(_:trigger:content:animation:)

**Initializer**

Cycles through a sequence of phases in response to changes in a specified value, animating updates to a view on each phase change.

## Declaration

```swift
init(_ phases: some Sequence<Phase>, trigger: some Equatable, @ViewBuilder content: @escaping (Phase) -> Content, animation: @escaping (Phase) -> Animation? = { _ in .default })
```

## Parameters

- **phases**: The sequence of phases to cycle through. Ensure that the sequence isn’t empty. If it is, SwiftUI logs a runtime warning and also returns a visual warning as the output view.
- **trigger**: A value whose changes cause the animator to use the next phase.
- **content**: A view builder closure that takes the current phase as an input. Return a view that’s based on the phase input.
- **animation**: A closure that takes the current phase as input. Return the animation to use when transitioning to the next phase. If you return `nil`, the transition doesn’t animate. If you don’t set this parameter, SwiftUI uses a default animation.

## Discussion

When the phase animator first appears, this initializer renders the `content` closure using the first phase as input to the closure. When the value of the `trigger` input changes, the animator reevaluates the `content` closure using the value from the second phase and animates the change. This procedure repeats with each successive phase until reaching the last phase, at which point the animator loops back to the first phase.

## Creating a phase animator

- **init(_:content:animation:)**: Cycles through a sequence of phases continuously, animating updates to a view on each phase change.

