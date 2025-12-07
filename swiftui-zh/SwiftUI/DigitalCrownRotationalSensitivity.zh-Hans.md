--- 来源：https://developer.apple.com/documentation/SwiftUI/DigitalCrownRotationalSensitivity
抓取时间：2025-12-02T17:42:25Z

---

# DigitalCrownRotationalSensitivity

**Enumeration**

在两个整数之间移动所需的数码表冠旋转角度。

## 声明

```swift
enum DigitalCrownRotationalSensitivity
```

## 概述

您可能需要进行一些实验，才能找到适合您使用场景的灵敏度级别。

## 获取灵敏度选项

- **DigitalCrownRotationalSensitivity.low**：低灵敏度。

- **DigitalCrownRotationalSensitivity.medium**：中等灵敏度。

- **DigitalCrownRotationalSensitivity.high**：高灵敏度。

## 与数码表冠交互

- **digitalCrownAccessory(_:)**：指定 Apple Watch 上数码表冠配件视图的可见性。

- **digitalCrownAccessory(content:)**：在 Apple Watch 的数码表冠旁边放置一个配件视图。

- **digitalCrownRotation(_:from:through:sensitivity:isContinuous:isHapticFeedbackEnabled:onChange:onIdle:)**：通过更新指定的绑定来跟踪数码表冠的旋转。

- **digitalCrownRotation(_:onChange:onIdle:)**：通过更新指定的绑定来跟踪数码表冠的旋转。

- **digitalCrownRotation(detent:from:through:by:sensitivity:isContinuous:isHapticFeedbackEnabled:onChange:onIdle:)**：通过更新指定的绑定来跟踪数码表冠的旋转。

- **digitalCrownRotation(_:)**：通过更新指定的绑定来跟踪数码表冠的旋转。

- **digitalCrownRotation(_:from:through:by:sensitivity:isContinuous:isHapticFeedbackEnabled:)**：通过更新指定的绑定来跟踪数码表冠的旋转。

- **DigitalCrownEvent**：用户旋转数码表冠时触发的事件。

## 符合以下规范

- 可复制

- 可等价比较

- 可哈希

- 可发送

- 可发送元数据类型


---
source: https://developer.apple.com/documentation/SwiftUI/DigitalCrownRotationalSensitivity
crawled: 2025-12-02T17:42:25Z
---

# DigitalCrownRotationalSensitivity

**Enumeration**

The amount of Digital Crown rotation needed to move between two integer numbers.

## Declaration

```swift
enum DigitalCrownRotationalSensitivity
```

## Overview

You may need to experiment to find the level of sensitivity that works for your use case.

## Getting sensitivity options

- **DigitalCrownRotationalSensitivity.low**: Low sensitivity.
- **DigitalCrownRotationalSensitivity.medium**: Medium sensitivity.
- **DigitalCrownRotationalSensitivity.high**: High sensitivity.

## Interacting with the Digital Crown

- **digitalCrownAccessory(_:)**: Specifies the visibility of Digital Crown accessory Views on Apple Watch.
- **digitalCrownAccessory(content:)**: Places an accessory View next to the Digital Crown on Apple Watch.
- **digitalCrownRotation(_:from:through:sensitivity:isContinuous:isHapticFeedbackEnabled:onChange:onIdle:)**: Tracks Digital Crown rotations by updating the specified binding.
- **digitalCrownRotation(_:onChange:onIdle:)**: Tracks Digital Crown rotations by updating the specified binding.
- **digitalCrownRotation(detent:from:through:by:sensitivity:isContinuous:isHapticFeedbackEnabled:onChange:onIdle:)**: Tracks Digital Crown rotations by updating the specified binding.
- **digitalCrownRotation(_:)**: Tracks Digital Crown rotations by updating the specified binding.
- **digitalCrownRotation(_:from:through:by:sensitivity:isContinuous:isHapticFeedbackEnabled:)**: Tracks Digital Crown rotations by updating the specified binding.
- **DigitalCrownEvent**: An event emitted when the user rotates the Digital Crown.

## Conforms To

- Copyable
- Equatable
- Hashable
- Sendable
- SendableMetatype

