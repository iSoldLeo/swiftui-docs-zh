---
来源：https://developer.apple.com/documentation/SwiftUI/Animation/spring(duration:bounce:blendDuration:)
抓取时间：2025-12-03T06:12:16Z
---

# spring(duration:bounce:blendDuration:)

**类型方法**

持续的弹簧动画。当与同一属性上的`spring()` 或 `interactiveSpring()` 动画混合时，每个动画都将被其后续动画取代，并保持从一个动画到下一个动画的速度。可选择在一段时间内混合弹簧之间的持续时间值。

## 声明

```swift
static func spring(duration: TimeInterval = 0.5, bounce: Double = 0.0, blendDuration: Double = 0) -> Animation
```

## 参数

- **duration**：感知持续时间，定义弹簧的节奏。它大致等同于稳定持续时间，但对于弹力很强的弹簧，它将是弹簧振荡周期的持续时间。
- **bounce**：弹簧应具有的弹力。0 表示无反弹（阻尼极小的弹簧），正值表示反弹程度增加，最大值为 1.0（相当于无阻尼振荡），负值表示过阻尼弹簧，最小值为-1.0。
- **blendDuration**：以秒为单位的持续时间，用于对持续时间的变化进行内插。

## 返回值

一个弹簧动画。

## 自定义弹簧动画

- **spring**：持久的弹簧动画。与同一属性上的`spring()` 或 `interactiveSpring()` 动画混合时，每个动画都将被其后续动画所取代，并保持从一个动画到下一个动画的速度。可选择在一段时间内混合弹簧之间的响应值。
- **spring(_:blendDuration:)**：持续的弹簧动画。
- **spring(response:dampingFraction:blendDuration:)**：持续的弹簧动画。与同一属性上的其他`spring()` 或 `interactiveSpring()` 动画混合时，每个动画都将被其后续动画取代，并保持从一个动画到下一个动画的速度。可选择在一段时间内混合弹簧之间的响应值。
- **interactiveSpring**：方便使用较低的`spring` 值，用于驱动交互式动画的`duration` 动画。
- **interactiveSpring(response:dampingFraction:blendDuration:)**：方便使用的`spring`动画，具有较低的`response`值，用于驱动交互式动画。
- **interpolatingSpring**：内插弹簧动画，使用阻尼弹簧模型在 [0, 1] 范围内产生数值，然后用于在动画属性的 [from, to] 范围内进行内插。通过添加每个动画的效果，在重叠动画中保持速度。
- **interpolatingSpring(_:initialVelocity:)**：内插弹簧动画，使用阻尼弹簧模型产生 1 到 0 之间的数值。
- **interpolatingSpring(duration:bounce:initialVelocity:)**：内插弹簧动画，使用阻尼弹簧模型在 [0, 1] 范围内产生数值，然后用于在动画属性的 [from, to] 范围内进行内插。通过添加每个动画的效果，在重叠动画中保持速度。
- **interpolatingSpring(mass:stiffness:damping:initialVelocity:)**：内插弹簧动画，使用阻尼弹簧模型在 [0, 1] 范围内产生数值，然后用于在动画属性的 [from, to] 范围内进行内插。通过添加每个动画的效果，在重叠动画中保持速度。


---
source: https://developer.apple.com/documentation/SwiftUI/Animation/spring(duration:bounce:blendDuration:)
crawled: 2025-12-03T06:12:16Z
---

# spring(duration:bounce:blendDuration:)

**Type Method**

A persistent spring animation. When mixed with other `spring()` or `interactiveSpring()` animations on the same property, each animation will be replaced by their successor, preserving velocity from one animation to the next. Optionally blends the duration values between springs over a time period.

## Declaration

```swift
static func spring(duration: TimeInterval = 0.5, bounce: Double = 0.0, blendDuration: Double = 0) -> Animation
```

## Parameters

- **duration**: The perceptual duration, which defines the pace of the spring. This is approximately equal to the settling duration, but for very bouncy springs, will be the duration of the period of oscillation for the spring.
- **bounce**: How bouncy the spring should be. A value of 0 indicates no bounces (a critically damped spring), positive values indicate increasing amounts of bounciness up to a maximum of 1.0 (corresponding to undamped oscillation), and negative values indicate overdamped springs with a minimum value of -1.0.
- **blendDuration**: The duration in seconds over which to interpolate changes to the duration.

## Return Value

A spring animation.

## Customizing spring animations

- **spring**: A persistent spring animation. When mixed with other `spring()` or `interactiveSpring()` animations on the same property, each animation will be replaced by their successor, preserving velocity from one animation to the next. Optionally blends the response values between springs over a time period.
- **spring(_:blendDuration:)**: A persistent spring animation.
- **spring(response:dampingFraction:blendDuration:)**: A persistent spring animation. When mixed with other `spring()` or `interactiveSpring()` animations on the same property, each animation will be replaced by their successor, preserving velocity from one animation to the next. Optionally blends the response values between springs over a time period.
- **interactiveSpring**: A convenience for a `spring` animation with a lower `duration` value, intended for driving interactive animations.
- **interactiveSpring(response:dampingFraction:blendDuration:)**: A convenience for a `spring` animation with a lower `response` value, intended for driving interactive animations.
- **interpolatingSpring**: An interpolating spring animation that uses a damped spring model to produce values in the range [0, 1] that are then used to interpolate within the [from, to] range of the animated property. Preserves velocity across overlapping animations by adding the effects of each animation.
- **interpolatingSpring(_:initialVelocity:)**: An interpolating spring animation that uses a damped spring model to produce values in the range of one to zero.
- **interpolatingSpring(duration:bounce:initialVelocity:)**: An interpolating spring animation that uses a damped spring model to produce values in the range [0, 1] that are then used to interpolate within the [from, to] range of the animated property. Preserves velocity across overlapping animations by adding the effects of each animation.
- **interpolatingSpring(mass:stiffness:damping:initialVelocity:)**: An interpolating spring animation that uses a damped spring model to produce values in the range [0, 1] that are then used to interpolate within the [from, to] range of the animated property. Preserves velocity across overlapping animations by adding the effects of each animation.

