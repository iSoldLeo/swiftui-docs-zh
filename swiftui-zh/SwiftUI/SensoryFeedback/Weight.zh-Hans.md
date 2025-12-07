---
来源： https://developer.apple.com/documentation/SwiftUI/SensoryFeedback/Weight
抓取时间： 2025-12-03T06:22:16Z
---

# SensoryFeedback.Weight

**Structure**

反馈类型所代表的权重。

## 声明

```swift
struct Weight
```

## 概览

`Weight` 值可传递给 `SensoryFeedback.impact(weight:intensity:)`。

## 获取灵活性值

- **light**：表示小型或轻量级 UI 对象之间发生碰撞。
- **medium**：表示中等大小或中等重量的 UI 对象之间发生碰撞。
- **heavy**：表示大型或重量级 UI 对象之间发生碰撞。

## 产生物理碰撞

- **impact**：提供一种物理隐喻，可用于补充视觉体验。
- **impact(weight:intensity:)**：提供了一个物理隐喻，可以用来补充视觉体验。
- **impact(flexibility:intensity:)**：提供了一个物理隐喻，可以用来补充视觉体验。
- **SensoryFeedback.Flexibility**：一种反馈类型所代表的灵活性。

## 符合

- 可等同
- 可发送
- 可发送元数据类型


---
source: https://developer.apple.com/documentation/SwiftUI/SensoryFeedback/Weight
crawled: 2025-12-03T06:22:16Z
---

# SensoryFeedback.Weight

**Structure**

The weight to be represented by a type of feedback.

## Declaration

```swift
struct Weight
```

## Overview

`Weight` values can be passed to `SensoryFeedback.impact(weight:intensity:)`.

## Getting flexibility values

- **light**: Indicates a collision between small or lightweight UI objects.
- **medium**: Indicates a collision between medium-sized or medium-weight UI objects.
- **heavy**: Indicates a collision between large or heavyweight UI objects.

## Producing a physical impact

- **impact**: Provides a physical metaphor you can use to complement a visual experience.
- **impact(weight:intensity:)**: Provides a physical metaphor you can use to complement a visual experience.
- **impact(flexibility:intensity:)**: Provides a physical metaphor you can use to complement a visual experience.
- **SensoryFeedback.Flexibility**: The flexibility to be represented by a type of feedback.

## Conforms To

- Equatable
- Sendable
- SendableMetatype

