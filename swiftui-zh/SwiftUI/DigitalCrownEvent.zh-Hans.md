--- 来源：https://developer.apple.com/documentation/SwiftUI/DigitalCrownEvent
抓取时间：2025-12-02T17:42:24Z

---

# DigitalCrownEvent

**Structure**

用户旋转数码表冠时触发的事件。

## 声明

```swift
struct DigitalCrownEvent
```

## 概述

使用 [digitalCrownRotation(_:)](View/digitalCrownRotation.zh-Hans.md) 修饰符接收这些事件。

## 获取事件

- **offset**：发送此事件时数码表冠的偏移量。

- **velocity**：发送此事件时偏移量变化的速度。

## 与数码表冠交互

- **digitalCrownAccessory(_:)**：指定 Apple Watch 上数码表冠配件视图的可见性。

- **digitalCrownAccessory(content:)**：在 Apple Watch 的数码表冠旁边放置一个配件视图。

- **digitalCrownRotation(_:from:through:sensitivity:isContinuous:isHapticFeedbackEnabled:onChange:onIdle:)**：通过更新指定的绑定来跟踪数码表冠的旋转。

- **digitalCrownRotation(_:onChange:onIdle:)**：通过更新指定的绑定来跟踪数码表冠的旋转。

- **digitalCrownRotation(detent:from:through:by:sensitivity:isContinuous:isHapticFeedbackEnabled:onChange:onIdle:)**：通过更新指定的绑定来跟踪数码表冠的旋转。

- **digitalCrownRotation(_:)**：通过更新指定的绑定来跟踪数码表冠的旋转。

- **digitalCrownRotation(_:from:through:by:sensitivity:isContinuous:isHapticFeedbackEnabled:)**：通过更新指定的绑定来跟踪数码表冠的旋转。

- **DigitalCrownRotationalSensitivity**：在两个整数之间移动所需的数码表冠旋转量。

## 符合以下标准

- Sendable

- SendableMetatype


---
source: https://developer.apple.com/documentation/SwiftUI/DigitalCrownEvent
crawled: 2025-12-02T17:42:24Z
---

# DigitalCrownEvent

**Structure**

An event emitted when the user rotates the Digital Crown.

## Declaration

```swift
struct DigitalCrownEvent
```

## Overview

Use the [digitalCrownRotation(_:)](View/digitalCrownRotation.zh-Hans.md) modifier to receive these events.

## Getting events

- **offset**: The offset of the digital crown when this event was sent.
- **velocity**: The velocity at which the offset was changing when this event was sent.

## Interacting with the Digital Crown

- **digitalCrownAccessory(_:)**: Specifies the visibility of Digital Crown accessory Views on Apple Watch.
- **digitalCrownAccessory(content:)**: Places an accessory View next to the Digital Crown on Apple Watch.
- **digitalCrownRotation(_:from:through:sensitivity:isContinuous:isHapticFeedbackEnabled:onChange:onIdle:)**: Tracks Digital Crown rotations by updating the specified binding.
- **digitalCrownRotation(_:onChange:onIdle:)**: Tracks Digital Crown rotations by updating the specified binding.
- **digitalCrownRotation(detent:from:through:by:sensitivity:isContinuous:isHapticFeedbackEnabled:onChange:onIdle:)**: Tracks Digital Crown rotations by updating the specified binding.
- **digitalCrownRotation(_:)**: Tracks Digital Crown rotations by updating the specified binding.
- **digitalCrownRotation(_:from:through:by:sensitivity:isContinuous:isHapticFeedbackEnabled:)**: Tracks Digital Crown rotations by updating the specified binding.
- **DigitalCrownRotationalSensitivity**: The amount of Digital Crown rotation needed to move between two integer numbers.

## Conforms To

- Sendable
- SendableMetatype

