--- 来源：https://developer.apple.com/documentation/SwiftUI/KeyframeAnimator
抓取时间：2025-12-02T17:27:18Z

---

# KeyframeAnimator

**Structure**

一个使用关键帧为其内容添加动画的容器。

## 声明

```swift
struct KeyframeAnimator<Value, KeyframePath, Content> where Value == KeyframePath.Value, KeyframePath : Keyframes, Content : View
```

## 概述

`content` 闭包会在动画过程中逐帧更新，因此请避免在 `content` 中直接执行任何耗时的操作。

## 创建阶段动画器

- **init(initialValue:repeating:content:keyframes:)**：持续循环给定的关键帧，并使用您在 `body` 中应用的修饰符更新视图。

- **init(initialValue:trigger:content:keyframes:)**：当给定的触发值发生变化时，播放指定的关键帧，并使用您在 `body` 中应用的修改器更新视图。

## 创建基于关键帧的动画

- **keyframeAnimator(initialValue:repeating:content:keyframes:)**：循环播放指定的关键帧，并使用您在 `body` 中应用的修改器更新视图。

- **keyframeAnimator(initialValue:trigger:content:keyframes:)**：当给定的触发值发生变化时，播放指定的关键帧，并使用您在 `body` 中应用的修改器更新视图。

- **Keyframes**：定义值随时间变化的类型。

- **KeyframeTimeline**：描述值如何随时间变化，使用关键帧建模。

- **KeyframeTrack**：一系列关键帧，用于动画化根类型的单个属性。

- **KeyframeTrackContentBuilder**：构建器，用于根据您在闭包中定义的关键帧创建关键帧轨道内容。

- **KeyframesBuilder**：构建器，用于将关键帧内容值合并为单个值。

- **KeyframeTrackContent**：一组关键帧，用于定义可动画值的插值曲线。

- **CubicKeyframe**：使用三次曲线在值之间平滑插值的关键帧。

- **LinearKeyframe**：使用简单线性插值的关键帧。

- **MoveKeyframe**：直接移动到给定值而不进行插值的关键帧。

- **SpringKeyframe**：使用弹簧函数插值到给定值的关键帧。

## 符合

- 视图


---
source: https://developer.apple.com/documentation/SwiftUI/KeyframeAnimator
crawled: 2025-12-02T17:27:18Z
---

# KeyframeAnimator

**Structure**

A container that animates its content with keyframes.

## Declaration

```swift
struct KeyframeAnimator<Value, KeyframePath, Content> where Value == KeyframePath.Value, KeyframePath : Keyframes, Content : View
```

## Overview

The `content` closure updates every frame while animating, so avoid performing any expensive operations directly within `content`.

## Creating a phase animator

- **init(initialValue:repeating:content:keyframes:)**: Loops the given keyframes continuously, updating the view using the modifiers you apply in `body`.
- **init(initialValue:trigger:content:keyframes:)**: Plays the given keyframes when the given trigger value changes, updating the view using the modifiers you apply in `body`.

## Creating keyframe-based animation

- **keyframeAnimator(initialValue:repeating:content:keyframes:)**: Loops the given keyframes continuously, updating the view using the modifiers you apply in `body`.
- **keyframeAnimator(initialValue:trigger:content:keyframes:)**: Plays the given keyframes when the given trigger value changes, updating the view using the modifiers you apply in `body`.
- **Keyframes**: A type that defines changes to a value over time.
- **KeyframeTimeline**: A description of how a value changes over time, modeled using keyframes.
- **KeyframeTrack**: A sequence of keyframes animating a single property of a root type.
- **KeyframeTrackContentBuilder**: The builder that creates keyframe track content from the keyframes that you define within a closure.
- **KeyframesBuilder**: A builder that combines keyframe content values into a single value.
- **KeyframeTrackContent**: A group of keyframes that define an interpolation curve of an animatable value.
- **CubicKeyframe**: A keyframe that uses a cubic curve to smoothly interpolate between values.
- **LinearKeyframe**: A keyframe that uses simple linear interpolation.
- **MoveKeyframe**: A keyframe that immediately moves to the given value without interpolating.
- **SpringKeyframe**: A keyframe that uses a spring function to interpolate to the given value.

## Conforms To

- View

