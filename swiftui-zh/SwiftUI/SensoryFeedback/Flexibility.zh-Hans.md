---
来源： https://developer.apple.com/documentation/SwiftUI/SensoryFeedback/Flexibility
抓取时间： 2025-12-03T06:22:15Z
---

# SensoryFeedback.Flexibility

**Structure**

反馈类型所代表的灵活性。

## 声明

```swift
struct Flexibility
```

## 概览

`Flexibility` 值可传递给 `SensoryFeedback.impact(flexibility:intensity:)`。

## 获取灵活性值

- **rigid**：表示硬或不灵活的用户界面对象之间发生碰撞。
- **soft**：表示软性或柔性 UI 对象之间发生碰撞。
- **solid**：表示中等柔性的实体 UI 对象之间发生碰撞。

## 产生物理碰撞

- **impact**：提供一种物理隐喻，可用于补充视觉体验。
- **impact(weight:intensity:)**：提供了一个物理隐喻，可以用来补充视觉体验。
- **impact(flexibility:intensity:)**：提供了一个物理隐喻，可以用来补充视觉体验。
- **SensoryFeedback.Weight**：反馈类型所代表的权重。

## 符合

- 等价
- 可发送
- 可发送元数据类型


---
source: https://developer.apple.com/documentation/SwiftUI/SensoryFeedback/Flexibility
crawled: 2025-12-03T06:22:15Z
---

# SensoryFeedback.Flexibility

**Structure**

The flexibility to be represented by a type of feedback.

## Declaration

```swift
struct Flexibility
```

## Overview

`Flexibility` values can be passed to `SensoryFeedback.impact(flexibility:intensity:)`.

## Getting flexibility values

- **rigid**: Indicates a collision between hard or inflexible UI objects.
- **soft**: Indicates a collision between soft or flexible UI objects.
- **solid**: Indicates a collision between solid UI objects of medium flexibility.

## Producing a physical impact

- **impact**: Provides a physical metaphor you can use to complement a visual experience.
- **impact(weight:intensity:)**: Provides a physical metaphor you can use to complement a visual experience.
- **impact(flexibility:intensity:)**: Provides a physical metaphor you can use to complement a visual experience.
- **SensoryFeedback.Weight**: The weight to be represented by a type of feedback.

## Conforms To

- Equatable
- Sendable
- SendableMetatype

