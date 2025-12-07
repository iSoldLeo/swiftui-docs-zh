--- 来源：https://developer.apple.com/documentation/SwiftUI/Controlling-the-timing-and-movements-of-your-animations

抓取时间：2025-12-02T15:50:58Z

---

# 控制动画的时序和运动

**示例代码**

使用相位和关键帧动画器构建可控的复杂动画。

## 概述

SwiftUI 提供了一系列实用的动画，您可以在应用中使用这些动画。这些动画通过提供视图和用户界面元素的视觉过渡，帮助增强应用的用户体验。虽然这些标准动画是增强应用用户交互的绝佳方式，但有时您需要更精确地控制视觉元素的时序和运动。[PhaseAnimator](PhaseAnimator.zh-Hans.md) 和 [KeyframeAnimator](KeyframeAnimator.zh-Hans.md) 可以帮助您实现这种控制。

阶段动画器允许您将动画定义为一系列称为阶段的离散步骤。动画器会循环执行这些阶段以创建视觉过渡。关键帧动画器允许您创建关键帧，这些关键帧定义了视觉过渡期间特定时间的动画值。

## 创建一个简单的弹跳动画

为了更好地理解如何使用 [PhaseAnimator](PhaseAnimator.zh-Hans.md) 或 [KeyframeAnimator](KeyframeAnimator.zh-Hans.md) 创建动画，我们先来看一个使用标准 SwiftUI 动画的简单示例。以下代码通过将表情符号的偏移量设置为 `-40.0` 来使其向上移动。为了实现平滑的移动过渡，代码使用 [withAnimation(_:_:)](withAnimation.zh-Hans.md) 函数在用户点击表情符号后应用 [bouncy](Animation/bouncy.zh-Hans.md) 动画。

```swift
struct SimpleAnimationView: View {
    var emoji: String
    @State private var offset = 0.0

    var body: some View {
        EmojiView(emoji: emoji)
            .offset(y: offset)
            .onTapGesture {
                withAnimation(.bouncy) {
                    offset = -40.0
                }
            }
    }
}
```

此动画只有一个离散步骤：将表情符号向上移动。然而，动画可以包含多个步骤，例如将表情符号向上移动，然后再返回到其原始位置。例如，以下代码将偏移量设置为 `-40.0` 以将表情符号向上移动，然后将偏移量 (`0.0`) 设置为将表情符号返回到其原始位置：

```swift
struct SimpleAnimationView: View {
    var emoji: String
    @State private var offset = 0.0

    var body: some View {
        EmojiView(emoji: emoji)
            .offset(y: offset)
            .onTapGesture {
                withAnimation(.bouncy) {
                    offset = -40.0
                } completion: {
                    withAnimation {
                        offset = 0.0
                    }
                }
            }
    }
}
```

此代码使用 [withAnimation(_:completionCriteria:_:completion:)](withAnimation___completionCriteria___completion.zh-Hans.md) 函数来实现视觉过渡的两个步骤。第一步发生在函数的闭包 `body` 中，将偏移量设置为 `-40.0`。第二步发生在闭包 `completion` 中，将偏移量设置为 `0.0`。

然而，`EmojiView` 实际上经历了三个步骤。第一步发生在视图首次出现时。视图`EmojiView`的偏移量为`0.0`。当用户点击视图时，偏移量变为`-40.0`；这是第二步。当该动画完成后，第三步会将偏移量变回`0.0`。然而，根据偏移量值（`0.0`和`-40.0`），实际上只有两个离散的步骤。

虽然这种实现方式确实可以正常工作，但使用[PhaseAnimator](PhaseAnimator.zh-Hans.md)来定义动画的离散步骤（即阶段）会更加方便。

## 使用阶段动画器实现弹跳效果

[PhaseAnimator](PhaseAnimator.zh-Hans.md)会自动按给定的阶段进行动画过渡。使用 [phaseAnimator(_:content:animation:)](View/phaseAnimator___content_animation.zh-Hans.md) 修饰符为动画器提供用于更改动画值的阶段。例如，前面显示的表情符号弹跳动画有两个阶段：向上移动和向后移动。您可以使用布尔值 `true` 和 `false` 来表示这些阶段。当阶段为 `true` 时，表情符号向上移动到 `-40.0`。当阶段为 `false` 时，表情符号通过将偏移量设置为 `0.0` 而返回到原始位置。

```swift
struct TwoPhaseAnimationView: View {
    var emoji: String
    
    var body: some View {
        EmojiView(emoji: emoji)
            .phaseAnimator([false, true]) { content, phase in
                content.offset(y: phase ? -40.0 : 0.0)
            }
    }
}
```

阶段动画器会按照您提供给 [phaseAnimator(_:content:animation:)](View/phaseAnimator___content_animation.zh-Hans.md) 修饰符的顺序循环遍历阶段列表。当视图首次出现时，阶段动画器会调用 `content` 闭包，并将第一阶段的值传递给它。然后，动画器会再次调用该闭包，并将第二阶段的值传递给它。对于每个后续阶段，动画器都会继续调用 `content` 闭包。到达最后一个阶段后，动画器会再次调用 `content` 闭包，并将第一阶段的值传递给它。

这意味着在前面的代码中，当视图首次出现时，阶段动画器会调用 `content` 闭包，并将阶段值 `false` 传递给它。这会将表情符号的偏移量设置为 `0.0`。然后，阶段动画器会调用 `content` 闭包，并将阶段值 `true` 传递给它。此阶段将偏移量设置为`-40.0`，使表情符号向上移动。到达该偏移位置后，动画器调用`content`，并将阶段设置为`false`。这将使表情符号通过将偏移量设置为`0.0`而返回到其原始位置。

此动画在视图出现时开始。要基于事件启动动画，请使用[phaseAnimator(_:trigger:content:animation:)](View/phaseAnimator___trigger_content_animation.zh-Hans.md)修饰符并提供一个`trigger`值，动画器会监听该值的变化。当该值发生变化时，动画器会启动动画。例如，以下代码会在每次有人点击表情符号时递增状态变量`likeCount`。该代码使用`likeCount`作为阶段动画器监听变化的值。现在，每当有人点击表情符号时，它都会向上移动并返回到原来的位置。

```swift
struct TwoPhaseAnimationView: View {
    var emoji: String
    @State private var likeCount = 1
    
    var body: some View {
        EmojiView(emoji: emoji)
            .phaseAnimator([false, true], trigger: likeCount) { content, phase in
                content.offset(y: phase ? -40.0 : 0.0)
            }
            .onTapGesture {
                likeCount += 1
            }
    }
}
```

目前，阶段动画器使用 [default](Animation/default.zh-Hans.md) 动画来移动表情符号。您可以通过为 `phaseAnimator` 修饰符提供一个动画闭包来更改此行为。在此闭包中，指定要为每个阶段应用的动画类型。例如，以下代码在阶段为 `true` 时应用 [bouncy](Animation/bouncy.zh-Hans.md) 动画；否则，应用 [default](Animation/default.zh-Hans.md) 动画：

```swift
struct TwoPhaseAnimationView: View {
    var emoji: String
    @State private var likeCount = 1
    
    var body: some View {
        EmojiView(emoji: emoji)
            .phaseAnimator([false, true], trigger: likeCount) { content, phase in
                content.offset(y: phase ? -40.0 : 0.0)
            } animation: { phase in
                phase ? .bouncy : .default
            }
            .onTapGesture {
                likeCount += 1
            }
    }
}
```

## 为动画添加更多阶段

虽然这种弹跳效果不错，但您可以为其添加更多炫酷元素。例如，您可以让表情符号在向上移动时逐渐增大，然后再缩小回正常大小。为此，您需要在动画中添加第三个阶段：缩放。

要定义各个阶段，请创建一个自定义类型来列出所有可能的阶段；例如：

```swift
private enum AnimationPhase: CaseIterable {
    case initial
    case move
    case scale
}
```

接下来，为了简化逻辑并降低复杂性，请定义计算属性来返回要动画的值。例如，要设置表情符号的垂直偏移量，请创建一个计算属性，该属性根据当前阶段返回偏移量：

```swift
private enum AnimationPhase: CaseIterable {
    case initial
    case move
    case scale
    
    var verticalOffset: Double {
        switch self {
        case .initial: 0
        case .move, .scale: -64
        }
    }
}
```

在初始阶段，偏移量为 `0`，这是表情符号的原始屏幕位置。但当阶段为 `move` 或 `scale` 时，偏移量为 `-64`。

您可以使用相同的方法（创建计算属性）来实现缩放效果，从而改变表情符号的大小。最初，表情符号以其原始大小显示，但在移动和缩放阶段会逐渐增大，如下图所示：

```swift
private enum AnimationPhase: CaseIterable {
    case initial
    case move
    case scale
    
    var verticalOffset: Double {
        switch self {
        case .initial: 0
        case .move, .scale: -64
        }
    }
    
    var scaleEffect: Double {
        switch self {
        case .initial: 1
        case .move, .scale: 1.5
        }
    }
}
```

要为表情符号添加动画效果，请将 [phaseAnimator(_:trigger:content:animation:)](View/phaseAnimator___trigger_content_animation.zh-Hans.md) 修饰符应用于 `EmojiView`。为动画器提供自定义类型 `AnimationPhase` 中的所有情况。然后，通过应用 [scaleEffect(_:anchor:)](View/scaleEffect___anchor.zh-Hans.md) 和 [offset(x:y:)](View/offset_x_y.zh-Hans.md) 修饰符，根据阶段更改内容。传递给这些修饰符的值来自计算属性，这有助于提高视图代码的可读性。

```swift
struct ThreePhaseAnimationView: View {
    var emoji: String
    @State private var likeCount = 1
    
    var body: some View {
        EmojiView(emoji: emoji)
            .phaseAnimator(AnimationPhase.allCases, trigger: likeCount) { content, phase in
                content
                    .scaleEffect(phase.scaleEffect)
                    .offset(y: phase.verticalOffset)
            } animation: { phase in
                switch phase {
                case .initial: .smooth
                case .move: .easeInOut(duration: 0.3)
                case .scale: .spring(duration: 0.3, bounce: 0.7)
                }
            }
            .onTapGesture {
                likeCount += 1
            }
    }
}
```

代码还会根据 `animation` 闭包中的阶段应用不同的动画类型，从而实现您想要的完整动画效果。

[PhaseAnimator](PhaseAnimator.zh-Hans.md) 允许您基于离散阶段控制动画，从而帮助您进一步完善动画。但如果您发现需要对动画的时序和运动进行更精细的控制，请使用 [KeyframeAnimator](KeyframeAnimator.zh-Hans.md)。

## 使用关键帧动画器获得更多控制

您可以使用 [KeyframeAnimator](KeyframeAnimator.zh-Hans.md) 定义复杂的、协调的动画，并完全控制动画的时序和运动。此动画器允许您创建关键帧，以定义动画过程中特定时间点的值。动画器使用这些值在动画的每一帧之间生成插值。

与阶段动画器（您需要对独立的、离散的状态进行建模）不同，关键帧动画器会生成您指定类型的插值。在动画播放过程中，动画器会在每一帧都提供这种类型的值，以便您可以通过应用修改器来更新动画视图。

您可以将类型定义为一个结构体，其中包含您想要独立设置动画的属性。例如，以下代码定义了四个属性，分别用于确定表情符号的缩放、拉伸、位置和角度：

```swift
private struct AnimationValues {
    var scale = 1.0
    var verticalStretch = 1.0
    var verticalOffset = 0.0
    var angle = Angle.zero
}
```

要使用关键帧动画器创建动画，请将 [keyframeAnimator(initialValue:repeating:content:keyframes:)](View/keyframeAnimator_initialValue_repeating_content_keyframes.zh-Hans.md) 或 [keyframeAnimator(initialValue:trigger:content:keyframes:)](View/keyframeAnimator_initialValue_trigger_content_keyframes.zh-Hans.md) 修改器应用于要设置动画的视图。例如，以下代码将第二个修改器应用于 `EmojiView`。动画的初始值是 `AnimationValues` 的一个新实例，状态变量 `likeCount` 是动画器用于检测变化的值，就像在之前的阶段动画示例中一样。

```swift
struct KeyframeAnimationView: View {
    var emoji: String
    @State private var likeCount = 1
    
    var body: some View {
        EmojiView(emoji: emoji)
            .keyframeAnimator(
                initialValue: AnimationValues(),
                trigger: likeCount
            ) { content, value in
                // ...
            } keyframes: { _ in
                // ...
            }
            .onTapGesture {
                likeCount += 1
            }
    }
}
```

要在动画期间对视图应用修改器，请向关键帧动画器提供一个 `content` 闭包。此闭包包含两个参数：

使用这些参数将修改器应用到 SwiftUI 正在制作动画的视图。例如，以下代码使用这些参数来旋转、缩放、拉伸和平移表情符号：

```swift
struct KeyframeAnimationView: View {
    var emoji: String
    @State private var likeCount = 1
    
    var body: some View {
        EmojiView(emoji: emoji)
            .keyframeAnimator(
                initialValue: AnimationValues(),
                trigger: likeCount
            ) { content, value in
                content
                    .rotationEffect(value.angle)
                    .scaleEffect(value.scale)
                    .scaleEffect(y: value.verticalStretch)
                    .offset(y: value.verticalOffset)
            } keyframes: { _ in
                // ...
            }
            .onTapGesture {
                likeCount += 1
            }
    }
}
```

接下来，定义关键帧。关键帧允许您使用不同的关键帧为不同的属性创建复杂的动画。为此，您需要将关键帧组织到轨道中。每个轨道控制您正在制作动画的不同类型的属性。您可以通过在创建轨道时提供属性的关键帧路径来将属性与轨道关联起来。例如，以下代码为属性 `scale` 添加一个 [KeyframeTrack](KeyframeTrack.zh-Hans.md)：

```swift
struct KeyframeAnimationView: View {
    var emoji: String
    @State private var likeCount = 1
    
    var body: some View {
        EmojiView(emoji: emoji)
            .keyframeAnimator(
                initialValue: AnimationValues(),
                trigger: likeCount
            ) { content, value in
                content
                    .rotationEffect(value.angle)
                    .scaleEffect(value.scale)
                    .scaleEffect(y: value.verticalStretch)
                    .offset(y: value.verticalOffset)
            } keyframes: { _ in
                KeyframeTrack(\.scale) {
                    // ...
                }
            }
            .onTapGesture {
                likeCount += 1
            }
    }
}
```

在创建轨道时，您可以使用 SwiftUI 中的声明式语法向轨道添加关键帧。关键帧有多种类型，例如 [CubicKeyframe](CubicKeyframe.zh-Hans.md)、[LinearKeyframe](LinearKeyframe.zh-Hans.md) 和 [SpringKeyframe](SpringKeyframe.zh-Hans.md)。您可以在一个轨道中混合使用不同类型的关键帧。例如，以下代码为属性 `scale` 添加一个轨道，该轨道执行线性动画和弹簧动画的组合：

```swift
struct KeyframeAnimationView: View {
    var emoji: String
    @State private var likeCount = 1
    
    var body: some View {
        EmojiView(emoji: emoji)
            .keyframeAnimator(
                initialValue: AnimationValues(),
                trigger: likeCount
            ) { content, value in
                content
                    .rotationEffect(value.angle)
                    .scaleEffect(value.scale)
                    .scaleEffect(y: value.verticalStretch)
                    .offset(y: value.verticalOffset)
            } keyframes: { _ in
                KeyframeTrack(\.scale) {
                    LinearKeyframe(1.0, duration: 0.36)
                    SpringKeyframe(1.5, duration: 0.8,
                        spring: .bouncy)
                    SpringKeyframe(1.0, spring: .bouncy)
                }
            }
            .onTapGesture {
                likeCount += 1
            }
    }
}
```

每种关键帧类型都会接收一个值。动画师使用此值在帧之间生成插值，并在调用动画师的内容闭包之前，设置轨道关键帧路径中指定的属性。例如，在前面的代码示例中，线性关键帧期间的缩放值为`1.0`，这使得表情符号保持其原始大小。然后在第一个弹簧关键帧期间，缩放值变为`1.5`，这导致表情符号变大。最后一个弹簧关键帧将缩放值设置为`1.0`，使表情符号恢复到其原始大小。

实现关键帧动画时，请为每个要设置动画的属性添加一个轨道。例如，`AnimationValues` 有四个属性：

- `scale`

- `verticalStretch`

- `verticalOffset`

- `angle`

要为这四个属性添加动画，动画师需要四个关键帧轨道，如下面的代码所示：

```swift
struct KeyframeAnimationView: View {
    var emoji: String
    @State private var likeCount = 1
    
    var body: some View {
        EmojiView(emoji: emoji)
            .keyframeAnimator(
                initialValue: AnimationValues(),
                trigger: likeCount
            ) { content, value in
                content
                    .rotationEffect(value.angle)
                    .scaleEffect(value.scale)
                    .scaleEffect(y: value.verticalStretch)
                    .offset(y: value.verticalOffset)
            } keyframes: { _ in
                KeyframeTrack(\.scale) {
                    LinearKeyframe(1.0, duration: 0.36)
                    SpringKeyframe(1.5, duration: 0.8, spring: .bouncy)
                    SpringKeyframe(1.0, spring: .bouncy)
                }
                
                KeyframeTrack(\.verticalOffset) {
                    LinearKeyframe(0.0, duration: 0.1)
                    SpringKeyframe(20.0, duration: 0.15, spring: .bouncy)
                    SpringKeyframe(-60.0, duration: 1.0, spring: .bouncy)
                    SpringKeyframe(0.0, spring: .bouncy)
                }

                KeyframeTrack(\.verticalStretch) {
                    CubicKeyframe(1.0, duration: 0.1)
                    CubicKeyframe(0.6, duration: 0.15)
                    CubicKeyframe(1.5, duration: 0.1)
                    CubicKeyframe(1.05, duration: 0.15)
                    CubicKeyframe(1.0, duration: 0.88)
                    CubicKeyframe(0.8, duration: 0.1)
                    CubicKeyframe(1.04, duration: 0.4)
                    CubicKeyframe(1.0, duration: 0.22)
                }

                KeyframeTrack(\.angle) {
                    CubicKeyframe(.zero, duration: 0.58)
                    CubicKeyframe(.degrees(16), duration: 0.125)
                    CubicKeyframe(.degrees(-16), duration: 0.125)
                    CubicKeyframe(.degrees(16), duration: 0.125)
                    CubicKeyframe(.zero, duration: 0.125)
                }
            }
            .onTapGesture {
                likeCount += 1
            }
    }
}
```

这些关键帧轨道的组合可以创建一个动画，该动画会挤压和拉伸表情符号，然后使其向上弹跳。当表情符号向上移动到最高点时，它会变大。当表情符号到达最高点时，它会轻微地抖动一下。然后，表情符号会带着轻微的弹跳回到原来的位置。

## 创建基于阶段的动画

- **phaseAnimator(_:content:animation:)**：为视图添加动画效果，使其在连续变化的阶段序列中呈现动画。

- **phaseAnimator(_:trigger:content:animation:)**：为视图添加动画效果，使其在基于触发器变化的阶段序列中呈现动画。

- **PhaseAnimator**：一个容器，通过自动循环播放您提供的一系列阶段来为其内容添加动画效果，每个阶段定义动画中的一个离散步骤。


---
source: https://developer.apple.com/documentation/SwiftUI/Controlling-the-timing-and-movements-of-your-animations
crawled: 2025-12-02T15:50:58Z
---

# Controlling the timing and movements of your animations

**Sample Code**

Build sophisticated animations that you control using phase and keyframe animators.

## Overview

SwiftUI provides a collection of useful animations that you can use in your app. These animations help enhance the user experience of your app by providing visual transitions of views and user interface elements. While these standard animations provide a great way to enhancement the user interaction of your app, there are times when you need to have more control over the timing and movement of a visual element. [PhaseAnimator](PhaseAnimator.zh-Hans.md) and [KeyframeAnimator](KeyframeAnimator.zh-Hans.md) help give you that control.

A phase animator allows you to define an animation as a collection of discrete steps called phases. The animator cycles through these phases to create a visual transition. With keyframe animator, you create keyframes that define animation values at specific times during the visual transition.

## Create a simple bounce animation

To better understand how to create animations using a [PhaseAnimator](PhaseAnimator.zh-Hans.md) or [KeyframeAnimator](KeyframeAnimator.zh-Hans.md), start with a simple example that uses standard SwiftUI animations. The following code moves an emoji upwards by setting its offset to `-40.0`. To provide a smooth transition of the movement, the code uses the [withAnimation(_:_:)](withAnimation.zh-Hans.md) function to apply a [bouncy](Animation/bouncy.zh-Hans.md) animation after someone taps the emoji.

```swift
struct SimpleAnimationView: View {
    var emoji: String
    @State private var offset = 0.0

    var body: some View {
        EmojiView(emoji: emoji)
            .offset(y: offset)
            .onTapGesture {
                withAnimation(.bouncy) {
                    offset = -40.0
                }
            }
    }
}
```

This animation has a single, discrete step: move the emoji upward. However, an animation can have multiple steps, such as moving an emoji upwards then back to its original position. For example, the following code sets the offset to `-40.0` to move the emoji upward, and then sets the offset (`0.0`) to return the emoji back to its original position:

```swift
struct SimpleAnimationView: View {
    var emoji: String
    @State private var offset = 0.0

    var body: some View {
        EmojiView(emoji: emoji)
            .offset(y: offset)
            .onTapGesture {
                withAnimation(.bouncy) {
                    offset = -40.0
                } completion: {
                    withAnimation {
                        offset = 0.0
                    }
                }
            }
    }
}
```

This code uses the [withAnimation(_:completionCriteria:_:completion:)](withAnimation___completionCriteria___completion.zh-Hans.md) function to animate the two steps of the visual transition. The first step occurs in the `body` closure of the function, setting the offset to `-40.0`. The second step occurs in the `completion` closure, setting the offset to `0.0`.



However, `EmojiView` actually goes through three steps. The first step happens when the view appears for the first time. The offset of the `EmojiView` view is `0.0`. When someone taps the view, the offset changes to `-40.0`; this is the second step. When that animation completes, the third step changes the offset back to `0.0`. However, there are only two discrete steps, based on the offset values (`0.0` and `-40.0`).

While this implementation certainly works as expected, using a [PhaseAnimator](PhaseAnimator.zh-Hans.md) is a more convenient way to define discrete steps as phases of an animation.

## Bounce with a phase animator

A [PhaseAnimator](PhaseAnimator.zh-Hans.md) automatically advances through a set of given phases to create an animated transition. Use the [phaseAnimator(_:content:animation:)](View/phaseAnimator___content_animation.zh-Hans.md) modifier to provide the animator the phases for changing the animation value. For example, the emoji bounce animation shown earlier has two phases: move up and move back. You can represent these phases using the Boolean values, `true` and `false`. When the phase is `true`, the emoji moves up to `-40.0`. When the phase is `false`, the emoji moves back to the original position by setting the offset to `0.0`.

```swift
struct TwoPhaseAnimationView: View {
    var emoji: String
    
    var body: some View {
        EmojiView(emoji: emoji)
            .phaseAnimator([false, true]) { content, phase in
                content.offset(y: phase ? -40.0 : 0.0)
            }
    }
}
```

The phase animator cycles through the list of phases in the order that you provide to the [phaseAnimator(_:content:animation:)](View/phaseAnimator___content_animation.zh-Hans.md) modifier. When the view first appears, the phase animator invokes the `content` closure passing in the first phase. Then the animator calls the closure with the value of the second phase. The animator continues to call the `content` closure for each additional phase. After reaching the last phase, the animator calls `content` one more time with the value of the first phase.

This means that in the previous code, the phase animator calls `content` with the phase value of `false` when the view first appears. This sets the emoji’s offset to `0.0`. The phase animator then calls `content` with the `true` phase. This phase sets the offset to `-40.0`, causing the emoji to move upwards. After reaching that offset position, the animator calls `content` with the phase of `false`. This causes the emoji to move back to its original position by setting its offset to `0.0`.

This animation starts when the view appears. To start the animation based on an event, use the [phaseAnimator(_:trigger:content:animation:)](View/phaseAnimator___trigger_content_animation.zh-Hans.md) modifier and provide a `trigger` value that animator observes for changes. The animator starts the animation when the value changes. For example, the following code increments the state variable `likeCount` each time a person taps the emoji. The code uses `likeCount` as the value that the phase animator observes for changes. Now whenever someone taps the emoji, it moves up and returns to its original position.

```swift
struct TwoPhaseAnimationView: View {
    var emoji: String
    @State private var likeCount = 1
    
    var body: some View {
        EmojiView(emoji: emoji)
            .phaseAnimator([false, true], trigger: likeCount) { content, phase in
                content.offset(y: phase ? -40.0 : 0.0)
            }
            .onTapGesture {
                likeCount += 1
            }
    }
}
```



So far, the phase animator uses the [default](Animation/default.zh-Hans.md) animation to move the emoji. You can change that behavior by providing the `phaseAnimator` modifier an animation closure. In this closure, specify the type of animation to apply for each phase. For instance, the following code applies a [bouncy](Animation/bouncy.zh-Hans.md) animation when the phase is `true`; otherwise, it applies the [default](Animation/default.zh-Hans.md) animation:

```swift
struct TwoPhaseAnimationView: View {
    var emoji: String
    @State private var likeCount = 1
    
    var body: some View {
        EmojiView(emoji: emoji)
            .phaseAnimator([false, true], trigger: likeCount) { content, phase in
                content.offset(y: phase ? -40.0 : 0.0)
            } animation: { phase in
                phase ? .bouncy : .default
            }
            .onTapGesture {
                likeCount += 1
            }
    }
}
```



## Add more phases to the animation

While this bounce effect is nice, you can add more pizzazz to it. For instance, you could make the emoji increase in size as it moves upward, and then shrink back to normal size. To do this, you’ll add a third phase to the animation: scale.

To define the phases, create a custom type that lists the possible phases; for example:

```swift
private enum AnimationPhase: CaseIterable {
    case initial
    case move
    case scale
}
```

Next, to help simplify logic and reduce complexity, define computed properties that return the values to animate. For instance, to set the vertical offset to move the emoji, create a computed property that returns the offset based on the current phase:

```swift
private enum AnimationPhase: CaseIterable {
    case initial
    case move
    case scale
    
    var verticalOffset: Double {
        switch self {
        case .initial: 0
        case .move, .scale: -64
        }
    }
}
```

When at the initial phase, the offset is `0`, which is the original screen location for the emoji. But when the phase is `move` or `scale`, the offset is `-64`.

You can use the same approach (creating a computed property) for the scale effect to change the size of the emoji. Initially, the emoji appears at its original size, but increases in size during the move and scale phase, as shown here:

```swift
private enum AnimationPhase: CaseIterable {
    case initial
    case move
    case scale
    
    var verticalOffset: Double {
        switch self {
        case .initial: 0
        case .move, .scale: -64
        }
    }
    
    var scaleEffect: Double {
        switch self {
        case .initial: 1
        case .move, .scale: 1.5
        }
    }
}
```

To animate an emoji, apply the [phaseAnimator(_:trigger:content:animation:)](View/phaseAnimator___trigger_content_animation.zh-Hans.md) modifier to the `EmojiView`. Provide the animator all cases from the custom `AnimationPhase` type. Then change the content based on the phase by applying the [scaleEffect(_:anchor:)](View/scaleEffect___anchor.zh-Hans.md) and [offset(x:y:)](View/offset_x_y.zh-Hans.md) modifiers. The values passed into these modifiers come from the computed properties, which helps keep the view code more readable.

```swift
struct ThreePhaseAnimationView: View {
    var emoji: String
    @State private var likeCount = 1
    
    var body: some View {
        EmojiView(emoji: emoji)
            .phaseAnimator(AnimationPhase.allCases, trigger: likeCount) { content, phase in
                content
                    .scaleEffect(phase.scaleEffect)
                    .offset(y: phase.verticalOffset)
            } animation: { phase in
                switch phase {
                case .initial: .smooth
                case .move: .easeInOut(duration: 0.3)
                case .scale: .spring(duration: 0.3, bounce: 0.7)
                }
            }
            .onTapGesture {
                likeCount += 1
            }
    }
}
```

The code also applies different animation types based on the phase in the `animation` closure to give the full animation that pizzazz you were looking for.





A [PhaseAnimator](PhaseAnimator.zh-Hans.md) gives you control of an animation based on discrete phases, which helps you add extra polish to an animation. But if you find that you need even more control over the timing and movement of an animation, use a [KeyframeAnimator](KeyframeAnimator.zh-Hans.md).

## Gain more control with a keyframe animator

You can define complex, coordinated animations with complete control over timing and movement using a [KeyframeAnimator](KeyframeAnimator.zh-Hans.md). This animator allows you to create keyframes that define values at specific times during an animation. The animator use these values to generate interpolated values in between each frame of the animation.

Unlike a phase animator, in which you model separate, discrete states, a keyframe animator generates interpolated values of the type that you specify. While an animation is in progress, the animator provides you with a value of this type on every frame so you can update the animating view by applying modifiers to it.

You define the type as a structure that contains the properties that you want to independently animate. For example, the following code defines four properties that determine the scale, stretch, position, and angle of an emoji:

```swift
private struct AnimationValues {
    var scale = 1.0
    var verticalStretch = 1.0
    var verticalOffset = 0.0
    var angle = Angle.zero
}
```



To create a animation using a keyframe animator, apply either the [keyframeAnimator(initialValue:repeating:content:keyframes:)](View/keyframeAnimator_initialValue_repeating_content_keyframes.zh-Hans.md) or [keyframeAnimator(initialValue:trigger:content:keyframes:)](View/keyframeAnimator_initialValue_trigger_content_keyframes.zh-Hans.md) modifier to the view that you want to animate. For instance, the following code applies the second modifier to `EmojiView`. The initial value for the animation is a new instance of `AnimationValues`, and the state variable `likeCount` is the value that the animator observes for changes as it did in the previous phase animation example.

```swift
struct KeyframeAnimationView: View {
    var emoji: String
    @State private var likeCount = 1
    
    var body: some View {
        EmojiView(emoji: emoji)
            .keyframeAnimator(
                initialValue: AnimationValues(),
                trigger: likeCount
            ) { content, value in
                // ...
            } keyframes: { _ in
                // ...
            }
            .onTapGesture {
                likeCount += 1
            }
    }
}
```

To apply modifiers to a view during the animation, provide a `content` closure to the keyframe animator. This closure includes two parameters:



Use these parameters to apply modifiers to the view that SwiftUI is animating. For example, the following code uses these parameters to rotate, scale, stretch, and move an emoji:

```swift
struct KeyframeAnimationView: View {
    var emoji: String
    @State private var likeCount = 1
    
    var body: some View {
        EmojiView(emoji: emoji)
            .keyframeAnimator(
                initialValue: AnimationValues(),
                trigger: likeCount
            ) { content, value in
                content
                    .rotationEffect(value.angle)
                    .scaleEffect(value.scale)
                    .scaleEffect(y: value.verticalStretch)
                    .offset(y: value.verticalOffset)
            } keyframes: { _ in
                // ...
            }
            .onTapGesture {
                likeCount += 1
            }
    }
}
```



Next, define the keyframes. Keyframes let you build sophisticated animations with different keyframe for different properties. To make this possible, you organize the keyframes into tracks. Each track controls a different property of the type that you are animating. You associate a property to a track by providing the key path to the property when creating the track. For example, the following code adds a [KeyframeTrack](KeyframeTrack.zh-Hans.md) for the `scale` property:

```swift
struct KeyframeAnimationView: View {
    var emoji: String
    @State private var likeCount = 1
    
    var body: some View {
        EmojiView(emoji: emoji)
            .keyframeAnimator(
                initialValue: AnimationValues(),
                trigger: likeCount
            ) { content, value in
                content
                    .rotationEffect(value.angle)
                    .scaleEffect(value.scale)
                    .scaleEffect(y: value.verticalStretch)
                    .offset(y: value.verticalOffset)
            } keyframes: { _ in
                KeyframeTrack(\.scale) {
                    // ...
                }
            }
            .onTapGesture {
                likeCount += 1
            }
    }
}
```

When creating a track, you use the declarative syntax in SwiftUI to add keyframes to the track. There are different kinds of keyframes, such as [CubicKeyframe](CubicKeyframe.zh-Hans.md), [LinearKeyframe](LinearKeyframe.zh-Hans.md), and [SpringKeyframe](SpringKeyframe.zh-Hans.md). You can mix and match the different kinds of keyframes within a track. For example, the following code adds a track for the `scale` property that performs a combination of linear and spring animations:

```swift
struct KeyframeAnimationView: View {
    var emoji: String
    @State private var likeCount = 1
    
    var body: some View {
        EmojiView(emoji: emoji)
            .keyframeAnimator(
                initialValue: AnimationValues(),
                trigger: likeCount
            ) { content, value in
                content
                    .rotationEffect(value.angle)
                    .scaleEffect(value.scale)
                    .scaleEffect(y: value.verticalStretch)
                    .offset(y: value.verticalOffset)
            } keyframes: { _ in
                KeyframeTrack(\.scale) {
                    LinearKeyframe(1.0, duration: 0.36)
                    SpringKeyframe(1.5, duration: 0.8,
                        spring: .bouncy)
                    SpringKeyframe(1.0, spring: .bouncy)
                }
            }
            .onTapGesture {
                likeCount += 1
            }
    }
}
```

Each keyframe type receives a value. The animator uses this value to generate interpolated values between frames and sets the property specified in the track’s key path before calling the animator’s content closure. For instance, in the previous code listing, the scale value is `1.0` during the linear keyframes, which keeps the emoji at its original size. Then the scale changes to `1.5` during the first spring keyframe. This causes the emoji to grow in size. The final spring keyframe sets the scale to `1.0`, which returns the emoji back to its original size.



When implementing a keyframe animation, include a track for each property that you want to animate. For instance, `AnimationValues` has four properties:

- `scale`
- `verticalStretch`
- `verticalOffset`
- `angle`

To animate all four, the animator needs four keyframe tracks as shown in the following code:

```swift
struct KeyframeAnimationView: View {
    var emoji: String
    @State private var likeCount = 1
    
    var body: some View {
        EmojiView(emoji: emoji)
            .keyframeAnimator(
                initialValue: AnimationValues(),
                trigger: likeCount
            ) { content, value in
                content
                    .rotationEffect(value.angle)
                    .scaleEffect(value.scale)
                    .scaleEffect(y: value.verticalStretch)
                    .offset(y: value.verticalOffset)
            } keyframes: { _ in
                KeyframeTrack(\.scale) {
                    LinearKeyframe(1.0, duration: 0.36)
                    SpringKeyframe(1.5, duration: 0.8, spring: .bouncy)
                    SpringKeyframe(1.0, spring: .bouncy)
                }
                
                KeyframeTrack(\.verticalOffset) {
                    LinearKeyframe(0.0, duration: 0.1)
                    SpringKeyframe(20.0, duration: 0.15, spring: .bouncy)
                    SpringKeyframe(-60.0, duration: 1.0, spring: .bouncy)
                    SpringKeyframe(0.0, spring: .bouncy)
                }

                KeyframeTrack(\.verticalStretch) {
                    CubicKeyframe(1.0, duration: 0.1)
                    CubicKeyframe(0.6, duration: 0.15)
                    CubicKeyframe(1.5, duration: 0.1)
                    CubicKeyframe(1.05, duration: 0.15)
                    CubicKeyframe(1.0, duration: 0.88)
                    CubicKeyframe(0.8, duration: 0.1)
                    CubicKeyframe(1.04, duration: 0.4)
                    CubicKeyframe(1.0, duration: 0.22)
                }

                KeyframeTrack(\.angle) {
                    CubicKeyframe(.zero, duration: 0.58)
                    CubicKeyframe(.degrees(16), duration: 0.125)
                    CubicKeyframe(.degrees(-16), duration: 0.125)
                    CubicKeyframe(.degrees(16), duration: 0.125)
                    CubicKeyframe(.zero, duration: 0.125)
                }
            }
            .onTapGesture {
                likeCount += 1
            }
    }
}
```

The combination of these keyframe tracks creates an animation that squishes and stretches the emoji, before bouncing it upwards. As the emoji moves towards its peak, it grows larger. When the emoji reaches its peak, it gives a little wiggle. Then the emoji returns to its original location with a slight bounce as it settles back into its original position.





## Creating phase-based animation

- **phaseAnimator(_:content:animation:)**: Animates effects that you apply to a view over a sequence of phases that change continuously.
- **phaseAnimator(_:trigger:content:animation:)**: Animates effects that you apply to a view over a sequence of phases that change based on a trigger.
- **PhaseAnimator**: A container that animates its content by automatically cycling through a collection of phases that you provide, each defining a discrete step within an animation.

