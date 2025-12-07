--- 来源：https://developer.apple.com/documentation/SwiftUI/SensoryFeedback

抓取时间：2025-12-02T17:36:11Z

---

# SensoryFeedback

**Structure**

表示一种可播放的触觉和/或音频反馈。

## 声明

```swift
struct SensoryFeedback
```

## 概述

此反馈可以传递给 `View.sensoryFeedback` 以播放。

## 指示开始和停止

- **start**：指示活动已启动。

- **stop**：指示活动已停止。

## 指示更改和选择

- **alignment**：指示拖动项的对齐方式。

- **decrease**：指示重要值已降至阈值以下。

- **increase**：指示重要值已升至阈值以上。

- **levelChange**：指示压力在不同级别之间的移动。

- **selection**：指示 UI 元素的值正在更改。

- **pathComplete**：指示绘制的路径已完成和/或已被识别。

## 指示操作结果

- **success**：指示任务或操作已完成。

- **warning**：表示某项任务或操作产生了某种警告。

- **error**：表示发生了错误。

## 产生物理影响

- **impact**：提供一种物理隐喻，可用于补充视觉体验。

- **impact(weight:intensity:)**：提供一种物理隐喻，可用于补充视觉体验。

- **impact(flexibility:intensity:)**：提供一种物理隐喻，可用于补充视觉体验。

- **SensoryFeedback.Flexibility**：可通过某种反馈类型来表示灵活性。

- **SensoryFeedback.Weight**：可通过某种反馈类型来表示重量。

## 结构体

- **SensoryFeedback.PressFeedback**：响应控件按下（触摸按下）事件而播放的反馈。

- **SensoryFeedback.ReleaseFeedback**：响应控件释放（触摸抬起）事件而播放的反馈。

- **SensoryFeedback.SelectionFeedback**：响应特定 UI 元素值变化而播放的反馈。

## 类型方法

- **press(_:)**：响应特定 UI 元素按下（触摸按下）事件而播放反馈。

- **release(_:)**：响应特定 UI 元素释放（触摸抬起）事件而播放反馈。

- **selection(_:)**：响应特定 UI 元素值变化而播放反馈。

## 提供触觉反馈

- **sensoryFeedback(_:trigger:)**：当提供的 `trigger` 值发生变化时，播放指定的 `feedback`。

- **sensoryFeedback(trigger:_:)**：当提供的 `trigger` 值发生变化后，`feedback` 闭包返回时，播放反馈。

- **sensoryFeedback(_:trigger:condition:)**：当提供的 `trigger` 值发生变化且 `condition` 闭包返回 `true` 时，播放指定的 `feedback`。

## 符合以下标准

- Equatable

- Sendable

- SendableMetatype


---
source: https://developer.apple.com/documentation/SwiftUI/SensoryFeedback
crawled: 2025-12-02T17:36:11Z
---

# SensoryFeedback

**Structure**

Represents a type of haptic and/or audio feedback that can be played.

## Declaration

```swift
struct SensoryFeedback
```

## Overview

This feedback can be passed to `View.sensoryFeedback` to play it.

## Indicating start and stop

- **start**: Indicates that an activity started.
- **stop**: Indicates that an activity stopped.

## Indicating changes and selections

- **alignment**: Indicates the alignment of a dragged item.
- **decrease**: Indicates that an important value decreased below a significant threshold.
- **increase**: Indicates that an important value increased above a significant threshold.
- **levelChange**: Indicates movement between discrete levels of pressure.
- **selection**: Indicates that a UI element’s values are changing.
- **pathComplete**: Indicates a drawn path has completed and/or recognized.

## Indicating the outcome of an operation

- **success**: Indicates that a task or action has completed.
- **warning**: Indicates that a task or action has produced a warning of some kind.
- **error**: Indicates that an error has occurred.

## Producing a physical impact

- **impact**: Provides a physical metaphor you can use to complement a visual experience.
- **impact(weight:intensity:)**: Provides a physical metaphor you can use to complement a visual experience.
- **impact(flexibility:intensity:)**: Provides a physical metaphor you can use to complement a visual experience.
- **SensoryFeedback.Flexibility**: The flexibility to be represented by a type of feedback.
- **SensoryFeedback.Weight**: The weight to be represented by a type of feedback.

## Structures

- **SensoryFeedback.PressFeedback**: Feedback that can be played in response to a press (touch down) on a control.
- **SensoryFeedback.ReleaseFeedback**: Feedback that can be played in response to a release (touch up) of a control.
- **SensoryFeedback.SelectionFeedback**: Feedback that can be played in response to a specific UI element’s values changing.

## Type Methods

- **press(_:)**: Plays feedback in response to a specific UI element being pressed (touch down).
- **release(_:)**: Plays feedback in response to a specific UI element being released (touch up).
- **selection(_:)**: Plays feedback in response to a specific UI element’s values changing.

## Providing haptic feedback

- **sensoryFeedback(_:trigger:)**: Plays the specified `feedback` when the provided `trigger` value changes.
- **sensoryFeedback(trigger:_:)**: Plays feedback when returned from the `feedback` closure after the provided `trigger` value changes.
- **sensoryFeedback(_:trigger:condition:)**: Plays the specified `feedback` when the provided `trigger` value changes and the `condition` closure returns `true`.

## Conforms To

- Equatable
- Sendable
- SendableMetatype

