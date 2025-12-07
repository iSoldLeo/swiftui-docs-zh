---
来源：https://developer.apple.com/documentation/SwiftUI/Animation/interactiveSpring(response:dampingFraction:blendDuration:)
抓取时间：2025-12-03T06:12:18Z
---

# interactiveSpring(response:dampingFraction:blendDuration:)

**类型方法**

一个方便的`spring`动画，具有较低的`response`值，用于驱动交互式动画。

### 声明

```swift
static func interactiveSpring(response: Double = 0.15, dampingFraction: Double = 0.86, blendDuration: TimeInterval = 0.25) -> Animation
```

## 自定义弹簧动画

- **spring**：持久的弹簧动画。与同一属性上的`spring()` 或 `interactiveSpring()` 动画混合时，每个动画都将被其后续动画所取代，并保持从一个动画到下一个动画的速度。可选择在一段时间内混合弹簧之间的响应值。
- **spring(_:blendDuration:)**：持续的弹簧动画。
- **spring(duration:bounce:blendDuration:)**：持续的弹簧动画。与同一属性上的其他`spring()` 或 `interactiveSpring()` 动画混合时，每个动画都将被其后续动画取代，并保持从一个动画到下一个动画的速度。可选择在一段时间内混合弹簧之间的持续时间值。
- **spring(response:dampingFraction:blendDuration:)**：持续的弹簧动画。与同一属性上的其他`spring()` 或`interactiveSpring()` 动画混合时，每个动画都将被其后续动画所取代，并保持从一个动画到下一个动画的速度。可选择在一段时间内混合弹簧之间的响应值。
- **interactiveSpring**：方便使用较低`duration` 值的`spring` 动画，用于驱动交互式动画。
- **interpolatingSpring**：内插弹簧动画，使用阻尼弹簧模型在 [0, 1] 范围内产生数值，然后用于在动画属性的 [from, to] 范围内进行内插。通过添加每个动画的效果，在重叠动画中保持速度。
- **interpolatingSpring(_:initialVelocity:)**：内插弹簧动画，使用阻尼弹簧模型产生 1 到 0 之间的数值。
- **interpolatingSpring(duration:bounce:initialVelocity:)**：内插弹簧动画，使用阻尼弹簧模型在 [0, 1] 范围内产生数值，然后用于在动画属性的 [from, to] 范围内进行内插。通过添加每个动画的效果，在重叠动画中保持速度。
- **interpolatingSpring(mass:stiffness:damping:initialVelocity:)**：内插弹簧动画，使用阻尼弹簧模型在 [0, 1] 范围内产生数值，然后用于在动画属性的 [from, to] 范围内进行内插。通过添加每个动画的效果，在重叠动画中保持速度。


---
source: https://developer.apple.com/documentation/SwiftUI/Animation/interactiveSpring(response:dampingFraction:blendDuration:)
crawled: 2025-12-03T06:12:18Z
---

# interactiveSpring(response:dampingFraction:blendDuration:)

**Type Method**

A convenience for a `spring` animation with a lower `response` value, intended for driving interactive animations.

## Declaration

```swift
static func interactiveSpring(response: Double = 0.15, dampingFraction: Double = 0.86, blendDuration: TimeInterval = 0.25) -> Animation
```

## Customizing spring animations

- **spring**: A persistent spring animation. When mixed with other `spring()` or `interactiveSpring()` animations on the same property, each animation will be replaced by their successor, preserving velocity from one animation to the next. Optionally blends the response values between springs over a time period.
- **spring(_:blendDuration:)**: A persistent spring animation.
- **spring(duration:bounce:blendDuration:)**: A persistent spring animation. When mixed with other `spring()` or `interactiveSpring()` animations on the same property, each animation will be replaced by their successor, preserving velocity from one animation to the next. Optionally blends the duration values between springs over a time period.
- **spring(response:dampingFraction:blendDuration:)**: A persistent spring animation. When mixed with other `spring()` or `interactiveSpring()` animations on the same property, each animation will be replaced by their successor, preserving velocity from one animation to the next. Optionally blends the response values between springs over a time period.
- **interactiveSpring**: A convenience for a `spring` animation with a lower `duration` value, intended for driving interactive animations.
- **interpolatingSpring**: An interpolating spring animation that uses a damped spring model to produce values in the range [0, 1] that are then used to interpolate within the [from, to] range of the animated property. Preserves velocity across overlapping animations by adding the effects of each animation.
- **interpolatingSpring(_:initialVelocity:)**: An interpolating spring animation that uses a damped spring model to produce values in the range of one to zero.
- **interpolatingSpring(duration:bounce:initialVelocity:)**: An interpolating spring animation that uses a damped spring model to produce values in the range [0, 1] that are then used to interpolate within the [from, to] range of the animated property. Preserves velocity across overlapping animations by adding the effects of each animation.
- **interpolatingSpring(mass:stiffness:damping:initialVelocity:)**: An interpolating spring animation that uses a damped spring model to produce values in the range [0, 1] that are then used to interpolate within the [from, to] range of the animated property. Preserves velocity across overlapping animations by adding the effects of each animation.

