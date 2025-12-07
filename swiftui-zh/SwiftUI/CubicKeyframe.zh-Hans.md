---
来源： https://developer.apple.com/documentation/SwiftUI/CubicKeyframe
抓取时间： 2025-12-02T17:33:57Z
---

# CubicKeyframe

**Structure**

使用立方曲线平滑插值的关键帧。

## 声明

```swift
struct CubicKeyframe<Value> where Value : Animatable
```

## 概览

如果不指定开始或结束速度，SwiftUI 会自动计算一条曲线，以保持关键帧之间的平滑运动。

相邻的立方体关键帧会产生 Catmull-Rom 样条曲线。

如果一个立方体关键帧紧跟着一个不同类型的关键帧（如线性关键帧），则前一个关键帧所定义线段的结束速度将被用作起始速度。

同样，如果在一个立方关键帧之后是另一种类型的关键帧，则下一个线段的初始速度将用作该关键帧所定义线段的末端速度。

## 创建关键帧

- **init(_:duration:startVelocity:endVelocity:)**：使用给定的值和时间戳创建新的关键帧。

## 创建基于关键帧的动画

- **keyframeAnimator(initialValue:repeating:content:keyframes:)**：连续循环给定的关键帧，使用在 `body` 中应用的修改器更新视图。
- **keyframeAnimator(initialValue:trigger:content:keyframes:)**：当给定的触发器值发生变化时播放给定的关键帧，并使用在 `body` 中应用的修改器更新视图。
- **KeyframeAnimator**：使用关键帧对其内容进行动画处理的容器。
- **Keyframes**：定义值随时间变化的类型。
- **KeyframeTimeline**：数值随时间变化的描述，使用关键帧建模。
- **KeyframeTrack**：为根类型的单个属性制作动画的关键帧序列。
- **KeyframeTrackContentBuilder**：根据您在闭包中定义的关键帧创建关键帧轨迹内容的构建器。
- **KeyframesBuilder**：将关键帧内容值合并为单一值的构建器。
- **KeyframeTrackContent**：定义动画值插值曲线的一组关键帧。
- **LinearKeyframe**：使用简单线性插值的关键帧。
- **MoveKeyframe**：使用简单线性插值的关键帧：不使用插值就立即移动到给定值的关键帧。
- **SpringKeyframe**：使用弹簧函数插值到给定值的关键帧。

## 符合

- 关键帧跟踪内容


---
source: https://developer.apple.com/documentation/SwiftUI/CubicKeyframe
crawled: 2025-12-02T17:33:57Z
---

# CubicKeyframe

**Structure**

A keyframe that uses a cubic curve to smoothly interpolate between values.

## Declaration

```swift
struct CubicKeyframe<Value> where Value : Animatable
```

## Overview

If you don’t specify a start or end velocity, SwiftUI automatically computes a curve that maintains smooth motion between keyframes.

Adjacent cubic keyframes result in a Catmull-Rom spline.

If a cubic keyframe follows a different type of keyframe, such as a linear keyframe, the end velocity of the segment defined by the previous keyframe will be used as the starting velocity.

Likewise, if a cubic keyframe is followed by a different type of keyframe, the initial velocity of the next segment is used as the end velocity of the segment defined by this keyframe.

## Creating the keyframe

- **init(_:duration:startVelocity:endVelocity:)**: Creates a new keyframe using the given value and timestamp.

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
- **LinearKeyframe**: A keyframe that uses simple linear interpolation.
- **MoveKeyframe**: A keyframe that immediately moves to the given value without interpolating.
- **SpringKeyframe**: A keyframe that uses a spring function to interpolate to the given value.

## Conforms To

- KeyframeTrackContent

