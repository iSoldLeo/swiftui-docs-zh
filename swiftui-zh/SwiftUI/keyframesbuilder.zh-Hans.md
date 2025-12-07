---
来源： https://developer.apple.com/documentation/swiftui/keyframesbuilder
抓取时间： 2025-12-04T13:14:41Z
---

# 关键帧生成器

**Structure**

将关键帧内容值合并为单一值的生成器。

## 声明

```swift
@resultBuilder struct KeyframesBuilder<Value>
```

## 建立关键帧

- **buildArray(_:)**
- **buildBlock()**
- **buildEither(first:)**
- **buildEither(second:)**
- **buildExpression(_:)**：关键帧
- **buildFinalResult(_:)**：关键帧
- **buildPartialBlock(accumulated:next:)**：关键帧
- **buildPartialBlock(first:)**

## 创建基于关键帧的动画

- **keyframeAnimator(initialValue:repeating:content:keyframes:)**：连续循环给定的关键帧，使用在 `body` 中应用的修改器更新视图。
- **keyframeAnimator(initialValue:trigger:content:keyframes:)**：当给定的触发器值发生变化时播放给定的关键帧，并使用在 `body` 中应用的修改器更新视图。
- **KeyframeAnimator**：使用关键帧对其内容进行动画处理的容器。
- **Keyframes**：定义值随时间变化的类型。
- **KeyframeTimeline**：数值随时间变化的描述，使用关键帧建模。
- **KeyframeTrack**：为根类型的单个属性制作动画的关键帧序列。
- **KeyframeTrackContentBuilder**：根据您在闭包中定义的关键帧创建关键帧轨迹内容的构建器。
- **KeyframeTrackContent**：定义动画值插值曲线的一组关键帧。
- **CubicKeyframe**：使用立方曲线在数值之间平滑插值的关键帧。
- **LinearKeyframe**：使用简单线性插值的关键帧。
- **MoveKeyframe**：不使用插值就立即移动到给定值的关键帧。
- **SpringKeyframe**：使用弹簧函数插值到给定值的关键帧。


---
source: https://developer.apple.com/documentation/swiftui/keyframesbuilder
crawled: 2025-12-04T13:14:41Z
---

# KeyframesBuilder

**Structure**

A builder that combines keyframe content values into a single value.

## Declaration

```swift
@resultBuilder struct KeyframesBuilder<Value>
```

## Building keyframes

- **buildArray(_:)**
- **buildBlock()**
- **buildEither(first:)**
- **buildEither(second:)**
- **buildExpression(_:)**: Keyframes
- **buildFinalResult(_:)**
- **buildPartialBlock(accumulated:next:)**
- **buildPartialBlock(first:)**

## Creating keyframe-based animation

- **keyframeAnimator(initialValue:repeating:content:keyframes:)**: Loops the given keyframes continuously, updating the view using the modifiers you apply in `body`.
- **keyframeAnimator(initialValue:trigger:content:keyframes:)**: Plays the given keyframes when the given trigger value changes, updating the view using the modifiers you apply in `body`.
- **KeyframeAnimator**: A container that animates its content with keyframes.
- **Keyframes**: A type that defines changes to a value over time.
- **KeyframeTimeline**: A description of how a value changes over time, modeled using keyframes.
- **KeyframeTrack**: A sequence of keyframes animating a single property of a root type.
- **KeyframeTrackContentBuilder**: The builder that creates keyframe track content from the keyframes that you define within a closure.
- **KeyframeTrackContent**: A group of keyframes that define an interpolation curve of an animatable value.
- **CubicKeyframe**: A keyframe that uses a cubic curve to smoothly interpolate between values.
- **LinearKeyframe**: A keyframe that uses simple linear interpolation.
- **MoveKeyframe**: A keyframe that immediately moves to the given value without interpolating.
- **SpringKeyframe**: A keyframe that uses a spring function to interpolate to the given value.

