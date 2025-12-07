--- 来源：https://developer.apple.com/documentation/swiftui/animation
抓取时间：2025-12-04T13:13:47Z

---

# 动画

**Structure**

视图随时间变化的方式，用于创建从一个状态到另一个状态的平滑视觉过渡。

## 声明

```swift
@frozen struct Animation
```

## 概述

`Animation` 用于在状态值从一个值变为另一个值时提供视图的视觉过渡。此过渡的特征因动画类型而异。例如，[linear](Animation/linear.zh-Hans.md) 动画会给人一种机械感，因为它的速度从开始到结束都保持一致。相比之下，使用缓动效果的动画（例如 [easeOut](Animation/easeOut.zh-Hans.md)）通过改变动画的加速度来提供更自然的感觉。

要为视图应用动画，请添加 [animation(_:value:)](View/animation___value.zh-Hans.md) 修饰符，并指定动画类型和要动画的值。例如，以下代码中的 [Circle](Circle.zh-Hans.md) 视图会在状态变量 `scale` 每次更改时执行 [easeIn](Animation/easeIn.zh-Hans.md) 动画：

```swift
struct ContentView: View {
    @State private var scale = 0.5

    var body: some View {
        VStack {
            Circle()
                .scaleEffect(scale)
                .animation(.easeIn, value: scale)
            HStack {
                Button("+") { scale += 0.1 }
                Button("-") { scale -= 0.1 }
            }
        }
        .padding()
    }
```

当 `scale` 的值更改时，修饰符 [scaleEffect(_:anchor:)](View/scaleEffect___anchor.zh-Hans.md) 会根据新值调整 [Circle](Circle.zh-Hans.md) 的大小。SwiftUI 可以对大小之间的过渡进行动画处理，因为 [Circle](Circle.zh-Hans.md) 符合 [Shape](Shape.zh-Hans.md) 协议。 SwiftUI 中的形状遵循 [Animatable](Animatable.zh-Hans.md) 协议，该协议描述了如何为视图的属性添加动画效果。

除了为视图添加动画之外，您还可以通过对动画类型应用动画修饰符来配置动画。例如，您可以：

- 使用 [delay(_:)](Animation/delay.zh-Hans.md) 修饰符延迟动画的开始时间。

- 使用 [repeatCount(_:autoreverses:)](Animation/repeatCount___autoreverses.zh-Hans.md) 或 [repeatForever(autoreverses:)](Animation/repeatForever_autoreverses.zh-Hans.md) 修饰符重复播放动画。

- 使用 [speed(_:)](Animation/speed.zh-Hans.md) 修饰符更改动画速度。

例如，以下代码中的视图 [Circle](Circle.zh-Hans.md) 通过使用 [repeatCount(_:autoreverses:)](Animation/repeatCount___autoreverses.zh-Hans.md) 修饰符，重复播放 [easeIn](Animation/easeIn.zh-Hans.md) 动画三次：

```swift
struct ContentView: View {
    @State private var scale = 0.5

    var body: some View {
        VStack {
            Circle()
                .scaleEffect(scale)
                .animation(.easeIn.repeatCount(3), value: scale)
            HStack {
                Button("+") { scale += 0.1 }
                Button("-") { scale -= 0.1 }
            }
        }
        .padding()
    }
}
```

视图还可以在绑定值更改时执行动画。要指定绑定的动画类型，请调用其 [animation(_:)](Binding/animation.zh-Hans.md) 方法。例如，以下代码中的视图执行 [linear](Animation/linear.zh-Hans.md) 动画，使厢式货车在视图的前缘和后缘之间移动。每次有人单击 [Toggle](Toggle.zh-Hans.md) 控件（该控件会更改 `$isTrailing` 绑定的值）时，货车都会移动。

```swift
struct ContentView: View {
    @State private var isTrailing = false

    var body: some View {
       VStack(alignment: isTrailing ? .trailing : .leading) {
            Image(systemName: "box.truck")
                .font(.system(size: 64))

            Toggle("Move to trailing edge",
                   isOn: $isTrailing.animation(.linear))
        }
    }
}
```

## 获取默认动画

- **default**：默认动画实例。

## 获取线性动画

- **linear**：以恒定速度移动的动画。

- **linear(duration:)**：在指定持续时间内以恒定速度移动的动画。

## 获取缓动动画

- **easeIn**：开始时速度较慢，然后在运动结束时逐渐加速的动画。

- **easeIn(duration:)**：具有指定持续时间的动画，开始时速度较慢，然后在运动结束时逐渐加速。

- **easeOut**：开始时速度较快，然后在运动结束时逐渐减速的动画。

- **easeOut(duration:)**：具有指定持续时间的动画，开始速度很快，然后在动作结束时逐渐减速。

- **easeInOut**：结合了缓入缓出动画效果的动画。

- **easeInOut(duration:)**：具有指定持续时间的动画，结合了缓入缓出动画效果。

## 获取内置弹簧动画

- **bouncy**：具有预定义持续时间和较大弹跳量的弹簧动画。

- **bouncy(duration:extraBounce:)**：具有预定义持续时间和较大弹跳量（可调节）的弹簧动画。

- **smooth**：具有预定义持续时间且无弹跳的平滑弹簧动画。

- **smooth(duration:extraBounce:)**：一种平滑的弹簧动画，具有预设的持续时间，无回弹，但可调节。

- **snappy**：一种弹簧动画，具有预设的持续时间和少量回弹，感觉更灵敏。

- **snappy(duration:extraBounce:)**：一种弹簧动画，具有预设的持续时间和少量回弹，感觉更灵敏，且可调节。

## 自定义弹簧动画

- **spring**：一种持续的弹簧动画。当与同一属性上的其他 `spring()` 或 `interactiveSpring()` 动画混合使用时，每个动画都会被其后续动画替换，从而保持动画之间的速度。可选择在一段时间内混合不同弹簧的响应值。

- **spring(_:blendDuration:)**：一种持续的弹簧动画。

- **spring(duration:bounce:blendDuration:)**：持久弹簧动画。当与同一属性上的其他 `spring()` 或 `interactiveSpring()` 动画混合使用时，每个动画都会被其后续动画替换，从而保持动画之间的速度。可选择在一段时间内混合不同弹簧的持续时间值。

- **spring(response:dampingFraction:blendDuration:)**：持久弹簧动画。当与同一属性上的其他 `spring()` 或 `interactiveSpring()` 动画混合使用时，每个动画都会被其后续动画替换，从而保持动画之间的速度。可选择在一段时间内混合不同弹簧的响应值。

- **interactiveSpring**：为 `spring` 动画提供便利，使其具有较低的 `duration` 值，旨在驱动交互式动画。

- **interactiveSpring(response:dampingFraction:blendDuration:)**：为 `spring` 动画提供便利，使其具有较低的 `response` 值，旨在驱动交互式动画。

- **interpolatingSpring**：一种插值弹簧动画，使用阻尼弹簧模型生成 [0, 1] 范围内的值，然后使用这些值在动画属性的 [from, to] 范围内进行插值。通过叠加每个动画的效果，保持重叠动画的速度一致。

- **interpolatingSpring(_:initialVelocity:)**：一种插值弹簧动画，使用阻尼弹簧模型生成 1 到 0 范围内的值。

- **interpolatingSpring(duration:bounce:initialVelocity:)**：一种插值弹簧动画，使用阻尼弹簧模型生成 [0, 1] 范围内的值，然后使用这些值在动画属性的 [from, to] 范围内进行插值。通过叠加每个动画的效果，保持重叠动画的速度一致。

- **interpolatingSpring(mass:stiffness:damping:initialVelocity:)**：一种插值弹簧动画，使用阻尼弹簧模型生成 [0, 1] 范围内的值，然后使用这些值在动画属性的 [from, to] 范围内进行插值。通过叠加每个动画的效果，保持重叠动画的速度一致。

## 创建自定义动画

- **init(_:)**：创建一个包含指定自定义动画的 `Animation`。

- **timingCurve(_:duration:)**：创建一个新动画，其速度由给定的曲线控制。

- **timingCurve(_:_:_:_:duration:)**：使用三次贝塞尔曲线创建动画。

## 配置动画

- **delay(_:)**：将动画的开始时间延迟指定的秒数。

- **repeatCount(_:autoreverses:)**：将动画重复播放指定的次数。

- **repeatForever(autoreverses:)**：在包含该动画的视图的生命周期内重复播放动画。

- **speed(_:)**：通过调整动画速度来改变动画的持续时间。

## 实例属性

- **base**

## 实例方法

- **animate(value:time:context:)**：计算动画的当前值。

- **logicallyComplete(after:)**：如果动画尚未逻辑完成，则在指定持续时间后，动画会报告逻辑完成。

- **shouldMerge(previous:value:time:context:)**：返回一个布尔值，指示当前动画是否应与之前的动画合并。

- **velocity(value:time:context:)**：计算动画的当前速度。

## 类型属性

- **systemOverlayAppearance**：系统叠加层出现时使用的动画。

- **systemOverlayDelayedDisappearance**：系统叠加层消失时使用的动画，延迟时间等于 `systemOverlayDisappearanceDelay`。

- **systemOverlayDisappearance**：系统叠加层消失时使用的动画。

- **systemOverlayDisappearanceDelay**：系统叠加层在消失前保持可见的时间长度。

## 类型方法

- **interactiveSpring(duration:extraBounce:blendDuration:)**：为 `spring` 动画提供便利，使其具有较低的 `response` 值，用于驱动交互式动画。

## 为操作添加基于状态的动画

- **withAnimation(_:_:)**：返回使用提供的动画重新计算视图主体的结果。

- **withAnimation(_:completionCriteria:_:completion:)**：返回使用提供的动画重新计算视图主体的结果，并在所有动画完成后运行完成操作。

- **AnimationCompletionCriteria**：确定动画何时完成的条件。

## 符合以下协议

- Copyable

- CustomDebugStringConvertible

- CustomReflectable

- CustomStringConvertible

- Equatable

- Hashable

- Sendable

- SendableMetatype


---
source: https://developer.apple.com/documentation/swiftui/animation
crawled: 2025-12-04T13:13:47Z
---

# Animation

**Structure**

The way a view changes over time to create a smooth visual transition from one state to another.

## Declaration

```swift
@frozen struct Animation
```

## Overview

An `Animation` provides a visual transition of a view when a state value changes from one value to another. The characteristics of this transition vary according to the animation type. For instance, a [linear](Animation/linear.zh-Hans.md) animation provides a mechanical feel to the animation because its speed is consistent from start to finish. In contrast, an animation that uses easing, like [easeOut](Animation/easeOut.zh-Hans.md), offers a more natural feel by varying the acceleration of the animation.

To apply an animation to a view, add the [animation(_:value:)](View/animation___value.zh-Hans.md) modifier, and specify both an animation type and the value to animate. For instance, the [Circle](Circle.zh-Hans.md) view in the following code performs an [easeIn](Animation/easeIn.zh-Hans.md) animation each time the state variable `scale` changes:

```swift
struct ContentView: View {
    @State private var scale = 0.5

    var body: some View {
        VStack {
            Circle()
                .scaleEffect(scale)
                .animation(.easeIn, value: scale)
            HStack {
                Button("+") { scale += 0.1 }
                Button("-") { scale -= 0.1 }
            }
        }
        .padding()
    }
```



When the value of `scale` changes, the modifier [scaleEffect(_:anchor:)](View/scaleEffect___anchor.zh-Hans.md) resizes [Circle](Circle.zh-Hans.md) according to the new value. SwiftUI can animate the transition between sizes because [Circle](Circle.zh-Hans.md) conforms to the [Shape](Shape.zh-Hans.md) protocol. Shapes in SwiftUI conform to the [Animatable](Animatable.zh-Hans.md) protocol, which describes how to animate a property of a view.

In addition to adding an animation to a view, you can also configure the animation by applying animation modifiers to the animation type. For example, you can:

- Delay the start of the animation by using the [delay(_:)](Animation/delay.zh-Hans.md) modifier.
- Repeat the animation by using the [repeatCount(_:autoreverses:)](Animation/repeatCount___autoreverses.zh-Hans.md) or [repeatForever(autoreverses:)](Animation/repeatForever_autoreverses.zh-Hans.md) modifiers.
- Change the speed of the animation by using the [speed(_:)](Animation/speed.zh-Hans.md) modifier.

For example, the [Circle](Circle.zh-Hans.md) view in the following code repeats the [easeIn](Animation/easeIn.zh-Hans.md) animation three times by using the [repeatCount(_:autoreverses:)](Animation/repeatCount___autoreverses.zh-Hans.md) modifier:

```swift
struct ContentView: View {
    @State private var scale = 0.5

    var body: some View {
        VStack {
            Circle()
                .scaleEffect(scale)
                .animation(.easeIn.repeatCount(3), value: scale)
            HStack {
                Button("+") { scale += 0.1 }
                Button("-") { scale -= 0.1 }
            }
        }
        .padding()
    }
}
```



A view can also perform an animation when a binding value changes. To specify the animation type on a binding, call its [animation(_:)](Binding/animation.zh-Hans.md) method. For example, the view in the following code performs a [linear](Animation/linear.zh-Hans.md) animation, moving the box truck between the leading and trailing edges of the view. The truck moves each time a person clicks the [Toggle](Toggle.zh-Hans.md) control, which changes the value of the `$isTrailing` binding.

```swift
struct ContentView: View {
    @State private var isTrailing = false

    var body: some View {
       VStack(alignment: isTrailing ? .trailing : .leading) {
            Image(systemName: "box.truck")
                .font(.system(size: 64))

            Toggle("Move to trailing edge",
                   isOn: $isTrailing.animation(.linear))
        }
    }
}
```



## Getting the default animation

- **default**: A default animation instance.

## Getting linear animations

- **linear**: An animation that moves at a constant speed.
- **linear(duration:)**: An animation that moves at a constant speed during a specified duration.

## Getting eased animations

- **easeIn**: An animation that starts slowly and then increases speed towards the end of the movement.
- **easeIn(duration:)**: An animation with a specified duration that starts slowly and then increases speed towards the end of the movement.
- **easeOut**: An animation that starts quickly and then slows towards the end of the movement.
- **easeOut(duration:)**: An animation with a specified duration that starts quickly and then slows towards the end of the movement.
- **easeInOut**: An animation that combines the behaviors of in and out easing animations.
- **easeInOut(duration:)**: An animation with a specified duration that combines the behaviors of in and out easing animations.

## Getting built-in spring animations

- **bouncy**: A spring animation with a predefined duration and higher amount of bounce.
- **bouncy(duration:extraBounce:)**: A spring animation with a predefined duration and higher amount of bounce that can be tuned.
- **smooth**: A smooth spring animation with a predefined duration and no bounce.
- **smooth(duration:extraBounce:)**: A smooth spring animation with a predefined duration and no bounce that can be tuned.
- **snappy**: A spring animation with a predefined duration and small amount of bounce that feels more snappy.
- **snappy(duration:extraBounce:)**: A spring animation with a predefined duration and small amount of bounce that feels more snappy and can be tuned.

## Customizing spring animations

- **spring**: A persistent spring animation. When mixed with other `spring()` or `interactiveSpring()` animations on the same property, each animation will be replaced by their successor, preserving velocity from one animation to the next. Optionally blends the response values between springs over a time period.
- **spring(_:blendDuration:)**: A persistent spring animation.
- **spring(duration:bounce:blendDuration:)**: A persistent spring animation. When mixed with other `spring()` or `interactiveSpring()` animations on the same property, each animation will be replaced by their successor, preserving velocity from one animation to the next. Optionally blends the duration values between springs over a time period.
- **spring(response:dampingFraction:blendDuration:)**: A persistent spring animation. When mixed with other `spring()` or `interactiveSpring()` animations on the same property, each animation will be replaced by their successor, preserving velocity from one animation to the next. Optionally blends the response values between springs over a time period.
- **interactiveSpring**: A convenience for a `spring` animation with a lower `duration` value, intended for driving interactive animations.
- **interactiveSpring(response:dampingFraction:blendDuration:)**: A convenience for a `spring` animation with a lower `response` value, intended for driving interactive animations.
- **interpolatingSpring**: An interpolating spring animation that uses a damped spring model to produce values in the range [0, 1] that are then used to interpolate within the [from, to] range of the animated property. Preserves velocity across overlapping animations by adding the effects of each animation.
- **interpolatingSpring(_:initialVelocity:)**: An interpolating spring animation that uses a damped spring model to produce values in the range of one to zero.
- **interpolatingSpring(duration:bounce:initialVelocity:)**: An interpolating spring animation that uses a damped spring model to produce values in the range [0, 1] that are then used to interpolate within the [from, to] range of the animated property. Preserves velocity across overlapping animations by adding the effects of each animation.
- **interpolatingSpring(mass:stiffness:damping:initialVelocity:)**: An interpolating spring animation that uses a damped spring model to produce values in the range [0, 1] that are then used to interpolate within the [from, to] range of the animated property. Preserves velocity across overlapping animations by adding the effects of each animation.

## Creating custom animations

- **init(_:)**: Create an `Animation` that contains the specified custom animation.
- **timingCurve(_:duration:)**: Creates a new animation with speed controlled by the given curve.
- **timingCurve(_:_:_:_:duration:)**: An animation created from a cubic Bézier timing curve.

## Configuring an animation

- **delay(_:)**: Delays the start of the animation by the specified number of seconds.
- **repeatCount(_:autoreverses:)**: Repeats the animation for a specific number of times.
- **repeatForever(autoreverses:)**: Repeats the animation for the lifespan of the view containing the animation.
- **speed(_:)**: Changes the duration of an animation by adjusting its speed.

## Instance Properties

- **base**

## Instance Methods

- **animate(value:time:context:)**: Calculates the current value of the animation.
- **logicallyComplete(after:)**: Causes the animation to report logical completion after the specified duration, if it has not already logically completed.
- **shouldMerge(previous:value:time:context:)**: Returns a Boolean value that indicates whether the current animation should merge with a previous animation.
- **velocity(value:time:context:)**: Calculates the current velocity of the animation.

## Type Properties

- **systemOverlayAppearance**: Animation used when system overlays appear.
- **systemOverlayDelayedDisappearance**: Animation used when system overlays disappear, with a delay equal to `systemOverlayDisappearanceDelay`.
- **systemOverlayDisappearance**: Animation used when system overlays disappear.
- **systemOverlayDisappearanceDelay**: The length of time system overlays remain visible before disappearing.

## Type Methods

- **interactiveSpring(duration:extraBounce:blendDuration:)**: A convenience for a `spring` animation with a lower `response` value, intended for driving interactive animations.

## Adding state-based animation to an action

- **withAnimation(_:_:)**: Returns the result of recomputing the view’s body with the provided animation.
- **withAnimation(_:completionCriteria:_:completion:)**: Returns the result of recomputing the view’s body with the provided animation, and runs the completion when all animations are complete.
- **AnimationCompletionCriteria**: The criteria that determines when an animation is considered finished.

## Conforms To

- Copyable
- CustomDebugStringConvertible
- CustomReflectable
- CustomStringConvertible
- Equatable
- Hashable
- Sendable
- SendableMetatype

