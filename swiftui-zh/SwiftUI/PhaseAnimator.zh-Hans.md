--- 来源：https://developer.apple.com/documentation/SwiftUI/PhaseAnimator
抓取时间：2025-12-02T16:16:04Z

---

# PhaseAnimator

**Structure**

一个容器，它通过自动循环播放您提供的一系列阶段来为其内容添加动画效果，每个阶段定义动画中的一个离散步骤。

## 声明

```swift
struct PhaseAnimator<Phase, Content> where Phase : Equatable, Content : View
```

## 概述

使用阶段动画器视图修饰符（例如 [phaseAnimator(_:content:animation:)](View/phaseAnimator___content_animation.zh-Hans.md)）在您的应用中创建阶段动画。

## 创建阶段动画器

- **init(_:content:animation:)**：连续循环播放一系列阶段，并在每个阶段切换时更新视图。

- **init(_:trigger:content:animation:)**：根据指定值的变化循环播放一系列阶段，并在每个阶段变化时更新视图动画。

## 创建基于阶段的动画

- **控制动画的时序和运动**：使用阶段和关键帧动画器构建并控制复杂的动画。

- **phaseAnimator(_:content:animation:)**：为应用于视图的效果添加动画，这些效果会随着一系列连续变化的阶段而变化。

- **phaseAnimator(_:trigger:content:animation:)**：为应用于视图的效果添加动画，这些效果会根据触发器变化，并随着一系列阶段而变化。

## 符合

- 视图


---
source: https://developer.apple.com/documentation/SwiftUI/PhaseAnimator
crawled: 2025-12-02T16:16:04Z
---

# PhaseAnimator

**Structure**

A container that animates its content by automatically cycling through a collection of phases that you provide, each defining a discrete step within an animation.

## Declaration

```swift
struct PhaseAnimator<Phase, Content> where Phase : Equatable, Content : View
```

## Overview

Use one of the phase animator view modifiers like [phaseAnimator(_:content:animation:)](View/phaseAnimator___content_animation.zh-Hans.md) to create a phased animation in your app.

## Creating a phase animator

- **init(_:content:animation:)**: Cycles through a sequence of phases continuously, animating updates to a view on each phase change.
- **init(_:trigger:content:animation:)**: Cycles through a sequence of phases in response to changes in a specified value, animating updates to a view on each phase change.

## Creating phase-based animation

- **Controlling the timing and movements of your animations**: Build sophisticated animations that you control using phase and keyframe animators.
- **phaseAnimator(_:content:animation:)**: Animates effects that you apply to a view over a sequence of phases that change continuously.
- **phaseAnimator(_:trigger:content:animation:)**: Animates effects that you apply to a view over a sequence of phases that change based on a trigger.

## Conforms To

- View

