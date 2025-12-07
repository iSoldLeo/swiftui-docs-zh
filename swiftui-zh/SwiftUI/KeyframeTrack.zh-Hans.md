--- 来源：https://developer.apple.com/documentation/SwiftUI/KeyframeTrack
抓取时间：2025-12-02T17:33:54Z

---

# KeyframeTrack

**Structure**

一系列关键帧，用于动画化根类型的单个属性。

## 声明

```swift
struct KeyframeTrack<Root, Value, Content> where Value == Content.Value, Content : KeyframeTrackContent
```

## 创建关键帧轨道

- **init(content:)**：创建一个实例，用于动画化从关键帧路径根节点开始的整个值。

- **init(_:content:)**：创建一个实例，用于动画化给定关键帧路径处根节点的属性。

## 创建基于关键帧的动画

- **keyframeAnimator(initialValue:repeating:content:keyframes:)**：循环播放指定的关键帧，并使用您在 `body` 中应用的修改器更新视图。

- **keyframeAnimator(initialValue:trigger:content:keyframes:)**：当指定的触发值发生变化时，播放指定的关键帧，并使用您在 `body` 中应用的修改器更新视图。

- **KeyframeAnimator**：一个使用关键帧为其内容添加动画的容器。

- **Keyframes**：一种定义值随时间变化的类型。

- **KeyframeTimeline**：描述值如何随时间变化的描述，使用关键帧进行建模。

- **KeyframeTrackContentBuilder**：一个构建器，用于根据您在闭包中定义的关键帧创建关键帧轨道内容。

- **KeyframesBuilder**：将关键帧内容值合并为单个值的构建器。

- **KeyframeTrackContent**：定义可动画值插值曲线的关键帧组。

- **CubicKeyframe**：使用三次曲线在值之间平滑插值的关键帧。

- **LinearKeyframe**：使用简单线性插值的关键帧。

- **MoveKeyframe**：直接移动到给定值而不进行插值的关键帧。

- **SpringKeyframe**：使用弹簧函数插值到给定值的关键帧。

## 符合

- 关键帧


---
source: https://developer.apple.com/documentation/SwiftUI/KeyframeTrack
crawled: 2025-12-02T17:33:54Z
---

# KeyframeTrack

**Structure**

A sequence of keyframes animating a single property of a root type.

## Declaration

```swift
struct KeyframeTrack<Root, Value, Content> where Value == Content.Value, Content : KeyframeTrackContent
```

## Creating a keyframe track

- **init(content:)**: Creates an instance that animates the entire value from the root of the key path.
- **init(_:content:)**: Creates an instance that animates the property of the root value at the given key path.

## Creating keyframe-based animation

- **keyframeAnimator(initialValue:repeating:content:keyframes:)**: Loops the given keyframes continuously, updating the view using the modifiers you apply in `body`.
- **keyframeAnimator(initialValue:trigger:content:keyframes:)**: Plays the given keyframes when the given trigger value changes, updating the view using the modifiers you apply in `body`.
- **KeyframeAnimator**: A container that animates its content with keyframes.
- **Keyframes**: A type that defines changes to a value over time.
- **KeyframeTimeline**: A description of how a value changes over time, modeled using keyframes.
- **KeyframeTrackContentBuilder**: The builder that creates keyframe track content from the keyframes that you define within a closure.
- **KeyframesBuilder**: A builder that combines keyframe content values into a single value.
- **KeyframeTrackContent**: A group of keyframes that define an interpolation curve of an animatable value.
- **CubicKeyframe**: A keyframe that uses a cubic curve to smoothly interpolate between values.
- **LinearKeyframe**: A keyframe that uses simple linear interpolation.
- **MoveKeyframe**: A keyframe that immediately moves to the given value without interpolating.
- **SpringKeyframe**: A keyframe that uses a spring function to interpolate to the given value.

## Conforms To

- Keyframes

