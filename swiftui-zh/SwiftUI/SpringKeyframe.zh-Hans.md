--- 来源：https://developer.apple.com/documentation/SwiftUI/SpringKeyframe

抓取时间：2025-12-02T17:33:59Z

---

# SpringKeyframe

**Structure**

使用弹簧函数插值到给定值的关键帧。

## 声明

```swift
struct SpringKeyframe<Value> where Value : Animatable
```

## 创建关键帧

- **init(_:duration:spring:startVelocity:)**：使用给定值和时间戳创建一个新的关键帧。

## 创建基于关键帧的动画

- **keyframeAnimator(initialValue:repeating:content:keyframes:)**：循环播放给定的关键帧，并使用 `body` 中应用的修饰符更新视图。

- **keyframeAnimator(initialValue:trigger:content:keyframes:)**：当给定的触发值发生变化时，播放指定的关键帧，并使用您在 `body` 中应用的修改器更新视图。

- **KeyframeAnimator**：一个使用关键帧为其内容添加动画的容器。

- **Keyframes**：一种定义值随时间变化的类型。

- **KeyframeTimeline**：描述值如何随时间变化的描述，使用关键帧进行建模。

- **KeyframeTrack**：一系列关键帧，用于为根类型的单个属性添加动画。

- **KeyframeTrackContentBuilder**：一个构建器，用于根据您在闭包中定义的关键帧创建关键帧轨道内容。

- **KeyframesBuilder**：将关键帧内容值合并为单个值的构建器。

- **KeyframeTrackContent**：定义可动画值插值曲线的关键帧组。

- **CubicKeyframe**：使用三次曲线在值之间平滑插值的关键帧。

- **LinearKeyframe**：使用简单线性插值的关键帧。

- **MoveKeyframe**：不进行插值直接移动到给定值的关键帧。

## 符合以下规范

- KeyframeTrackContent


---
source: https://developer.apple.com/documentation/SwiftUI/SpringKeyframe
crawled: 2025-12-02T17:33:59Z
---

# SpringKeyframe

**Structure**

A keyframe that uses a spring function to interpolate to the given value.

## Declaration

```swift
struct SpringKeyframe<Value> where Value : Animatable
```

## Creating the keyframe

- **init(_:duration:spring:startVelocity:)**: Creates a new keyframe using the given value and timestamp.

## Creating keyframe-based animation

- **keyframeAnimator(initialValue:repeating:content:keyframes:)**: Loops the given keyframes continuously, updating the view using the modifiers you apply in `body`.
- **keyframeAnimator(initialValue:trigger:content:keyframes:)**: Plays the given keyframes when the given trigger value changes, updating the view using the modifiers you apply in `body`.
- **KeyframeAnimator**: A container that animates its content with keyframes.
- **Keyframes**: A type that defines changes to a value over time.
- **KeyframeTimeline**: A description of how a value changes over time, modeled using keyframes.
- **KeyframeTrack**: A sequence of keyframes animating a single property of a root type.
- **KeyframeTrackContentBuilder**: The builder that creates keyframe track content from the keyframes that you define within a closure.
- **KeyframesBuilder**: A builder that combines keyframe content values into a single value.
- **KeyframeTrackContent**: A group of keyframes that define an interpolation curve of an animatable value.
- **CubicKeyframe**: A keyframe that uses a cubic curve to smoothly interpolate between values.
- **LinearKeyframe**: A keyframe that uses simple linear interpolation.
- **MoveKeyframe**: A keyframe that immediately moves to the given value without interpolating.

## Conforms To

- KeyframeTrackContent

