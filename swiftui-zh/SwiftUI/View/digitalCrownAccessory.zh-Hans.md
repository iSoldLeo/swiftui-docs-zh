--- 来源：https://developer.apple.com/documentation/SwiftUI/View/digitalCrownAccessory(_:)

抓取时间：2025-12-02T17:42:20Z

---

# digitalCrownAccessory(_:)

**实例方法**

指定 Apple Watch 上数码表冠配件视图的可见性。

## 声明

```swift
nonisolated func digitalCrownAccessory(_ visibility: Visibility) -> some View

```

## 参数

- **visibility**：数码表冠配件的可见性。

## 说明

使用此方法可以自定义使用 `View/digitalCrownAccessory(_ content:)` 修饰符创建的数码表冠配件 `View` 的可见性。您可能希望即使数码表冠指示器不可见，配件也保持可见，以便指示滚动表冠的操作。

## 与数码表冠交互

- **digitalCrownAccessory(content:)**：在 Apple Watch 的数码表冠旁边放置一个配件视图。

- **digitalCrownRotation(_:from:through:sensitivity:isContinuous:isHapticFeedbackEnabled:onChange:onIdle:)**：通过更新指定的绑定来跟踪数码表冠的旋转。

- **digitalCrownRotation(_:onChange:onIdle:)**：通过更新指定的绑定来跟踪数码表冠的旋转。

- **digitalCrownRotation(detent:from:through:by:sensitivity:isContinuous:isHapticFeedbackEnabled:onChange:onIdle:)**：通过更新指定的绑定来跟踪数码表冠的旋转。

- **digitalCrownRotation(_:)**：通过更新指定的绑定来跟踪数码表冠的旋转。

- **digitalCrownRotation(_:from:through:by:sensitivity:isContinuous:isHapticFeedbackEnabled:)**：通过更新指定的绑定来跟踪数码表冠的旋转。

- **DigitalCrownEvent**：用户旋转数码表冠时触发的事件。

- **DigitalCrownRotationalSensitivity**：在两个整数之间移动所需的数码表冠旋转量。


---
source: https://developer.apple.com/documentation/SwiftUI/View/digitalCrownAccessory(_:)
crawled: 2025-12-02T17:42:20Z
---

# digitalCrownAccessory(_:)

**Instance Method**

Specifies the visibility of Digital Crown accessory Views on Apple Watch.

## Declaration

```swift
nonisolated func digitalCrownAccessory(_ visibility: Visibility) -> some View

```

## Parameters

- **visibility**: The visibility of the digital crown accessory.

## Discussion

Use this method to customize the visibility of a Digital Crown accessory `View` created with the `View/digitalCrownAccessory(_ content:)` modifier. You may want to keep an accessory visible even when the Digital Crown Indicator is not visible to indicate what scrolling the crown will do.

## Interacting with the Digital Crown

- **digitalCrownAccessory(content:)**: Places an accessory View next to the Digital Crown on Apple Watch.
- **digitalCrownRotation(_:from:through:sensitivity:isContinuous:isHapticFeedbackEnabled:onChange:onIdle:)**: Tracks Digital Crown rotations by updating the specified binding.
- **digitalCrownRotation(_:onChange:onIdle:)**: Tracks Digital Crown rotations by updating the specified binding.
- **digitalCrownRotation(detent:from:through:by:sensitivity:isContinuous:isHapticFeedbackEnabled:onChange:onIdle:)**: Tracks Digital Crown rotations by updating the specified binding.
- **digitalCrownRotation(_:)**: Tracks Digital Crown rotations by updating the specified binding.
- **digitalCrownRotation(_:from:through:by:sensitivity:isContinuous:isHapticFeedbackEnabled:)**: Tracks Digital Crown rotations by updating the specified binding.
- **DigitalCrownEvent**: An event emitted when the user rotates the Digital Crown.
- **DigitalCrownRotationalSensitivity**: The amount of Digital Crown rotation needed to move between two integer numbers.

