--- 来源：https://developer.apple.com/documentation/SwiftUI/View/phaseAnimator(_:content:animation:)

抓取时间：2025-12-02T16:16:02Z

---

# phaseAnimator(_:content:animation:)

**实例方法**

为视图应用动画效果，使其在连续变化的阶段序列中循环播放。

## 声明

```swift
nonisolated func phaseAnimator<Phase>(_ phases: some Sequence, @ViewBuilder content: @escaping (PlaceholderContentView<Self>, Phase) -> some View, animation: @escaping (Phase) -> Animation? = { _ in .default }) -> some View where Phase : Equatable

```

## 参数

- **phases**：要循环播放的阶段序列。请确保序列不为空。如果为空，SwiftUI 会记录运行时警告，并在输出视图中返回视觉警告。

- **content**：一个视图构建器闭包，接受两个参数：一个表示已修改视图的代理值和当前阶段。您可以根据当前阶段为代理应用效果。

- **animation**：一个闭包，以当前阶段作为输入。返回过渡到下一阶段时使用的动画。如果返回 `nil`，则过渡不会有动画效果。如果未设置此参数，SwiftUI 将使用默认动画。

## 讨论

当修改后的视图首次出现时，此修饰符会使用第一阶段作为闭包的输入，并渲染其 `content` 闭包，同时还会渲染一个修改后视图的代理。根据第一阶段的值，将效果应用到代理视图（从而也应用到修改后的视图）。

修饰符会立即将第二阶段的值提供给其 `content` 闭包。相应地更新应用于代理视图的效果，修饰符会自动生成动画效果。动画完成后，该过程会重复执行，依次进入下一个阶段，直到到达最后一个阶段。此时，修改器会循环回到第一个阶段。

## 创建基于阶段的动画

- **控制动画的时序和运动**：使用阶段和关键帧动画器构建并控制复杂的动画。

- **phaseAnimator(_:trigger:content:animation:)**：根据触发器，将应用于视图的效果按阶段序列进行动画处理。

- **PhaseAnimator**：一个容器，它通过自动循环播放您提供的一系列阶段来为其内容添加动画效果，每个阶段定义动画中的一个独立步骤。


---
source: https://developer.apple.com/documentation/SwiftUI/View/phaseAnimator(_:content:animation:)
crawled: 2025-12-02T16:16:02Z
---

# phaseAnimator(_:content:animation:)

**Instance Method**

Animates effects that you apply to a view over a sequence of phases that change continuously.

## Declaration

```swift
nonisolated func phaseAnimator<Phase>(_ phases: some Sequence, @ViewBuilder content: @escaping (PlaceholderContentView<Self>, Phase) -> some View, animation: @escaping (Phase) -> Animation? = { _ in .default }) -> some View where Phase : Equatable

```

## Parameters

- **phases**: The sequence of phases to cycle through. Ensure that the sequence isn’t empty. If it is, SwiftUI logs a runtime warning and also returns a visual warning as the output view.
- **content**: A view builder closure that takes two parameters: a proxy value representing the modified view and the current phase. You can apply effects to the proxy based on the current phase.
- **animation**: A closure that takes the current phase as input. Return the animation to use when transitioning to the next phase. If you return `nil`, the transition doesn’t animate. If you don’t set this parameter, SwiftUI uses a default animation.

## Discussion

When the modified view first appears, this modifier renders its `content` closure using the first phase as input to the closure, along with a proxy for the modified view. Apply effects to the proxy — and thus to the modified view — in a way that’s appropriate for the first phase value.

Right away, the modifier provides its `content` closure with the value of the second phase. Update the effects that you apply to the proxy view accordingly, and the modifier animates the change for you. As soon as the animation completes, the procedure repeats using successive phases until reaching the last phase, at which point the modifier loops back to the first phase.

## Creating phase-based animation

- **Controlling the timing and movements of your animations**: Build sophisticated animations that you control using phase and keyframe animators.
- **phaseAnimator(_:trigger:content:animation:)**: Animates effects that you apply to a view over a sequence of phases that change based on a trigger.
- **PhaseAnimator**: A container that animates its content by automatically cycling through a collection of phases that you provide, each defining a discrete step within an animation.

