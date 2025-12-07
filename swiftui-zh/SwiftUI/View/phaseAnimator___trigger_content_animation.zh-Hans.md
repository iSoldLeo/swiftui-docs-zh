--- 来源：https://developer.apple.com/documentation/SwiftUI/View/phaseAnimator(_:trigger:content:animation:)

抓取时间：2025-12-02T16:16:03Z

---

# phaseAnimator(_:trigger:content:animation:)

**实例方法**

为视图应用动画效果，使其在触发条件改变的一系列阶段中循环播放。

## 声明

```swift
nonisolated func phaseAnimator<Phase>(_ phases: some Sequence, trigger: some Equatable, @ViewBuilder content: @escaping (PlaceholderContentView<Self>, Phase) -> some View, animation: @escaping (Phase) -> Animation? = { _ in .default }) -> some View where Phase : Equatable

```

## 参数

- **phases**：要循环播放的阶段序列。请确保序列不为空。如果为空，SwiftUI 会记录运行时警告，并在输出视图中返回视觉警告。

- **trigger**：一个值，其变化会导致动画器使用下一个阶段。

- **content**：一个视图构建器闭包，接受两个参数：一个代表修改后视图的代理值和一个当前阶段。您可以根据当前阶段对代理应用效果。

- **animation**：一个闭包，以当前阶段作为输入。返回过渡到下一阶段时使用的动画。如果返回 `nil`，则过渡不会有动画效果。如果未设置此参数，SwiftUI 将使用默认动画。

## 讨论

当修改后的视图首次出现时，此修饰符会使用第一个阶段作为闭包的输入，并结合修改后视图的代理来渲染其 `content` 闭包。根据第一个阶段的值，以适当的方式对代理（从而对修改后的视图）应用效果。

之后，当 `trigger` 输入的值发生变化时，修改器会将第二阶段的值传递给其 `content` 闭包。相应地更新应用于代理视图的效果，修改器会自动生成动画。下次 `trigger` 输入发生变化时，此过程会重复执行，使用连续的阶段，直到到达最后一个阶段，此时修改器会循环回到第一个阶段。

## 创建基于阶段的动画

- **控制动画的时序和运动**：使用阶段和关键帧动画器构建可控制的复杂动画。

- **phaseAnimator(_:content:animation:)**：为应用于视图的效果生成动画，使其在连续变化的阶段序列上呈现动画效果。

- **PhaseAnimator**：一个容器，它通过自动循环播放您提供的多个阶段来为其内容添加动画效果，每个阶段定义动画中的一个独立步骤。


---
source: https://developer.apple.com/documentation/SwiftUI/View/phaseAnimator(_:trigger:content:animation:)
crawled: 2025-12-02T16:16:03Z
---

# phaseAnimator(_:trigger:content:animation:)

**Instance Method**

Animates effects that you apply to a view over a sequence of phases that change based on a trigger.

## Declaration

```swift
nonisolated func phaseAnimator<Phase>(_ phases: some Sequence, trigger: some Equatable, @ViewBuilder content: @escaping (PlaceholderContentView<Self>, Phase) -> some View, animation: @escaping (Phase) -> Animation? = { _ in .default }) -> some View where Phase : Equatable

```

## Parameters

- **phases**: The sequence of phases to cycle through. Ensure that the sequence isn’t empty. If it is, SwiftUI logs a runtime warning and also returns a visual warning as the output view.
- **trigger**: A value whose changes cause the animator to use the next phase.
- **content**: A view builder closure that takes two parameters: a proxy value representing the modified view and the current phase. You can apply effects to the proxy based on the current phase.
- **animation**: A closure that takes the current phase as input. Return the animation to use when transitioning to the next phase. If you return `nil`, the transition doesn’t animate. If you don’t set this parameter, SwiftUI uses a default animation.

## Discussion

When the modified view first appears, this modifier renders its `content` closure using the first phase as input to the closure, along with a proxy for the modified view. Apply effects to the proxy — and thus to the modified view — in a way that’s appropriate for the first phase value.

Later, when the value of the `trigger` input changes, the modifier provides its `content` closure with the value of the second phase. Update the effects that you apply to the proxy view accordingly, and the modifier animates the change for you. The next time the `trigger` input changes, this procedure repeats using successive phases until reaching the last phase, at which point the modifier loops back to the first phase.

## Creating phase-based animation

- **Controlling the timing and movements of your animations**: Build sophisticated animations that you control using phase and keyframe animators.
- **phaseAnimator(_:content:animation:)**: Animates effects that you apply to a view over a sequence of phases that change continuously.
- **PhaseAnimator**: A container that animates its content by automatically cycling through a collection of phases that you provide, each defining a discrete step within an animation.

