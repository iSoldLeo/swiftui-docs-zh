--- 来源：https://developer.apple.com/documentation/SwiftUI/KeyframeTimeline
抓取时间：2025-12-02T17:33:53Z

---

# KeyframeTimeline

**Structure**

使用关键帧来描述值随时间的变化。

## 声明

```swift
struct KeyframeTimeline<Value>
```

## 概述

与 SwiftUI 中的其他动画（使用 [Animation](Animation.zh-Hans.md)）不同，关键帧不会在 SwiftUI 提供的状态变化的起始值和目标值之间进行插值。相反，关键帧使用构成其主体的轨道来完整定义值随时间变化的路径。

`Keyframes` 值大致类似于视频片段；它们具有固定的持续时间，您可以拖动并评估持续时间内的任意时间点。

`Keyframes` 结构还允许您计算特定时间的插值，以便在将关键帧集成到自定义用例中时使用该值。

例如，您可以使用 `Keyframes` 实例来定义符合 `Animatable:` 类型的动画。

```swift
let keyframes = KeyframeTimeline(initialValue: CGPoint.zero) {
    CubicKeyframe(.init(x: 0, y: 100), duration: 0.3)
    CubicKeyframe(.init(x: 0, y: 0), duration: 0.7)
}

let value = keyframes.value(time: 0.45)
```

对于涉及多个协调变化的动画，您可以包含多个嵌套轨道：

```swift
struct Values {
    var rotation = Angle.zero
    var scale = 1.0
}

let keyframes = KeyframeTimeline(initialValue: Values()) {
    KeyframeTrack(\.rotation) {
        CubicKeyframe(.zero, duration: 0.2)
        CubicKeyframe(.degrees(45), duration: 0.3)
    }
    KeyframeTrack(\.scale) {
        CubicKeyframe(value: 1.2, duration: 0.5)
        CubicKeyframe(value: 0.9, duration: 0.2)
        CubicKeyframe(value: 1.0, duration: 0.3)
    }
}
```

多个嵌套轨道会按照声明顺序更新初始值。这意味着，如果多个嵌套轨道更改根值的同一属性，则将使用最后一个竞争轨道的值。

## 创建关键帧时间线

- **init(initialValue:content:)**：使用您提供的初始值和内容创建一个新实例。

## 获取持续时间

- **duration**：内容持续时间（以秒为单位）。

## 获取插值

- **value(time:)**：返回指定时间点的插值。

- **value(progress:)**：返回指定进度（0 到 1 之间）的插值。

## 创建基于关键帧的动画

- **keyframeAnimator(initialValue:repeating:content:keyframes:)**：循环播放指定的关键帧，并使用 `body` 中设置的修改器更新视图。

- **keyframeAnimator(initialValue:trigger:content:keyframes:)**：当触发值发生变化时播放指定的关键帧，并使用 `body` 中设置的修改器更新视图。

- **KeyframeAnimator**：一个使用关键帧为其内容添加动画的容器。

- **Keyframes**：一种定义值随时间变化的类型。

- **KeyframeTrack**：一系列关键帧，用于为根类型的单个属性添加动画。

- **KeyframeTrackContentBuilder**：一个构建器，用于根据您在闭包中定义的关键帧创建关键帧轨道内容。

- **KeyframesBuilder**：一个构建器，用于将关键帧内容值合并为单个值。

- **KeyframeTrackContent**：一组关键帧，用于定义可动画值的插值曲线。

- **CubicKeyframe**：一个关键帧，使用三次曲线在值之间平滑插值。

- **LinearKeyframe**：使用简单线性插值的关键帧。

- **MoveKeyframe**：直接移动到给定值而不进行插值的关键帧。

- **SpringKeyframe**：使用弹簧函数插值到给定值的关键帧。


---
source: https://developer.apple.com/documentation/SwiftUI/KeyframeTimeline
crawled: 2025-12-02T17:33:53Z
---

# KeyframeTimeline

**Structure**

A description of how a value changes over time, modeled using keyframes.

## Declaration

```swift
struct KeyframeTimeline<Value>
```

## Overview

Unlike other animations in SwiftUI (using [Animation](Animation.zh-Hans.md)), keyframes don’t interpolate between from and to values that SwiftUI provides as state changes. Instead, keyframes fully define the path that a value takes over time using the tracks that make up their body.

`Keyframes` values are roughly analogous to video clips; they have a set duration, and you can scrub and evaluate them for any time within the duration.

The `Keyframes` structure also allows you to compute an interpolated value at a specific time, which you can use when integrating keyframes into custom use cases.

For example, you can use a `Keyframes` instance to define animations for a type conforming to `Animatable:`

```swift
let keyframes = KeyframeTimeline(initialValue: CGPoint.zero) {
    CubicKeyframe(.init(x: 0, y: 100), duration: 0.3)
    CubicKeyframe(.init(x: 0, y: 0), duration: 0.7)
}

let value = keyframes.value(time: 0.45)
```

For animations that involve multiple coordinated changes, you can include multiple nested tracks:

```swift
struct Values {
    var rotation = Angle.zero
    var scale = 1.0
}

let keyframes = KeyframeTimeline(initialValue: Values()) {
    KeyframeTrack(\.rotation) {
        CubicKeyframe(.zero, duration: 0.2)
        CubicKeyframe(.degrees(45), duration: 0.3)
    }
    KeyframeTrack(\.scale) {
        CubicKeyframe(value: 1.2, duration: 0.5)
        CubicKeyframe(value: 0.9, duration: 0.2)
        CubicKeyframe(value: 1.0, duration: 0.3)
    }
}
```

Multiple nested tracks update the initial value in the order that they are declared. This means that if multiple nested plans change the same property of the root value, the value from the last competing track will be used.

## Creating a keyframe timeline

- **init(initialValue:content:)**: Creates a new instance using the initial value and content that you provide.

## Getting the duration

- **duration**: The duration of the content in seconds.

## Getting an interpolated value

- **value(time:)**: Returns the interpolated value at the given time.
- **value(progress:)**: Returns the interpolated value at the given progress in the range zero to one.

## Creating keyframe-based animation

- **keyframeAnimator(initialValue:repeating:content:keyframes:)**: Loops the given keyframes continuously, updating the view using the modifiers you apply in `body`.
- **keyframeAnimator(initialValue:trigger:content:keyframes:)**: Plays the given keyframes when the given trigger value changes, updating the view using the modifiers you apply in `body`.
- **KeyframeAnimator**: A container that animates its content with keyframes.
- **Keyframes**: A type that defines changes to a value over time.
- **KeyframeTrack**: A sequence of keyframes animating a single property of a root type.
- **KeyframeTrackContentBuilder**: The builder that creates keyframe track content from the keyframes that you define within a closure.
- **KeyframesBuilder**: A builder that combines keyframe content values into a single value.
- **KeyframeTrackContent**: A group of keyframes that define an interpolation curve of an animatable value.
- **CubicKeyframe**: A keyframe that uses a cubic curve to smoothly interpolate between values.
- **LinearKeyframe**: A keyframe that uses simple linear interpolation.
- **MoveKeyframe**: A keyframe that immediately moves to the given value without interpolating.
- **SpringKeyframe**: A keyframe that uses a spring function to interpolate to the given value.

