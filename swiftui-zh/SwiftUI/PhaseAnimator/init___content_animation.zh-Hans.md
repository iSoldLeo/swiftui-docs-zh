---
来源：https://developer.apple.com/documentation/SwiftUI/PhaseAnimator/init(_:内容:动画:)
抓取时间：2025-12-02T20:59:18Z
---

# init(_:content:animation:)

**Initializer**

连续循环播放一系列相位，在每个相位变化时都会以动画形式更新视图。

## 声明

```swift
init(_ phases: some Sequence<Phase>, @ViewBuilder content: @escaping (Phase) -> Content, animation: @escaping (Phase) -> Animation? = { _ in .default })
```

## 参数

- **phases**：要循环播放的阶段序列。确保序列不是空的。如果为空，SwiftUI 将记录运行时警告，并返回可视警告作为输出视图。
- **content**：视图构建器闭包，将当前阶段作为输入。返回基于当前阶段的视图。
- **animation**：将当前阶段作为输入的闭包。返回过渡到下一阶段时使用的动画。如果返回 `nil`，则过渡不会产生动画。如果不设置此参数，SwiftUI 将使用默认动画。

## 讨论

当相位动画播放器首次出现时，该初始化程序会使用第一个相位作为闭包的输入，渲染`content` 闭包。然后，动画播放器立即开始为视图播放动画，视图是通过使用从`animation` 闭包返回的动画将第二阶段发送到`content` 闭包而生成的。在到达最后一个阶段之前，动画制作者会在连续的阶段中重复这一过程，然后再次循环到第一个阶段。

## 创建阶段动画

- **init(_:trigger:content:animation:)**：根据指定值的变化循环播放一连串的阶段，在每个阶段变化时对视图进行动画更新。


---
source: https://developer.apple.com/documentation/SwiftUI/PhaseAnimator/init(_:content:animation:)
crawled: 2025-12-02T20:59:18Z
---

# init(_:content:animation:)

**Initializer**

Cycles through a sequence of phases continuously, animating updates to a view on each phase change.

## Declaration

```swift
init(_ phases: some Sequence<Phase>, @ViewBuilder content: @escaping (Phase) -> Content, animation: @escaping (Phase) -> Animation? = { _ in .default })
```

## Parameters

- **phases**: The sequence of phases to cycle through. Ensure that the sequence isn’t empty. If it is, SwiftUI logs a runtime warning and also returns a visual warning as the output view.
- **content**: A view builder closure that takes the current phase as an input. Return a view that’s based on the current phase.
- **animation**: A closure that takes the current phase as input. Return the animation to use when transitioning to the next phase. If you return `nil`, the transition doesn’t animate. If you don’t set this parameter, SwiftUI uses a default animation.

## Discussion

When the phase animator first appears, this initializer renders the `content` closure using the first phase as input to the closure. The animator then begins immediately animating to the view produced by sending the second phase to the `content` closure using the animation returned from the `animation` closure. This procedure repeats for successive phases until reaching the last phase, after which the animator loops back to the first phase again.

## Creating a phase animator

- **init(_:trigger:content:animation:)**: Cycles through a sequence of phases in response to changes in a specified value, animating updates to a view on each phase change.

