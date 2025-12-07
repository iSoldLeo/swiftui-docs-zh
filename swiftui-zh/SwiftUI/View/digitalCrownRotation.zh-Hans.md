--- 来源：https://developer.apple.com/documentation/SwiftUI/View/digitalCrownRotation(_:)

抓取时间：2025-12-02T17:42:23Z

---

# digitalCrownRotation(_:)

**实例方法**

通过更新指定的绑定来跟踪数码表冠的旋转。

## 声明

```swift
nonisolated func digitalCrownRotation<V>(_ binding: Binding<V>) -> some View where V : BinaryFloatingPoint

```

## 参数

- **binding**：一个绑定到某个值的绑定，该值会随着用户旋转数码表冠而更新。隐式范围为 `(-infinity, +infinity)`。

## 说明

使用此方法可以在用户旋转 Apple Watch 上的数码表冠时接收您提供的绑定值。以下示例会接收绑定值的变化，从 `0.0` 开始，并根据用户旋转数码表冠的方向递增或递减：

```swift
struct DigitalCrown: View {
    @State private var crownValue = 0.0

    var body: some View {
        Text("Received Value:\(crownValue, specifier: "%.1f")")
            .focusable()
            .digitalCrownRotation($crownValue)
    }
}
```

## 与数码表冠交互

- **digitalCrownAccessory(_:)**：指定 Apple Watch 上数码表冠配件视图的可见性。

- **digitalCrownAccessory(content:)**：在 Apple Watch 的数码表冠旁边放置一个配件视图。

- **digitalCrownRotation(_:from:through:sensitivity:isContinuous:isHapticFeedbackEnabled:onChange:onIdle:)**：通过更新指定的绑定值来跟踪数码表冠的旋转。

- **digitalCrownRotation(_:onChange:onIdle:)**：通过更新指定的绑定值来跟踪数码表冠的旋转。

- **digitalCrownRotation(detent:from:through:by:sensitivity:isContinuous:isHapticFeedbackEnabled:onChange:onIdle:)**：通过更新指定的绑定值来跟踪数码表冠的旋转。

- **digitalCrownRotation(_:from:through:by:sensitivity:isContinuous:isHapticFeedbackEnabled:)**：通过更新指定的绑定来跟踪数码表冠的旋转。

- **DigitalCrownEvent**：用户旋转数码表冠时触发的事件。

- **DigitalCrownRotationalSensitivity**：在两个整数之间移动所需的数码表冠旋转量。


---
source: https://developer.apple.com/documentation/SwiftUI/View/digitalCrownRotation(_:)
crawled: 2025-12-02T17:42:23Z
---

# digitalCrownRotation(_:)

**Instance Method**

Tracks Digital Crown rotations by updating the specified binding.

## Declaration

```swift
nonisolated func digitalCrownRotation<V>(_ binding: Binding<V>) -> some View where V : BinaryFloatingPoint

```

## Parameters

- **binding**: A binding to a value that updates as the user rotates the Digital Crown. The implicit range is `(-infinity, +infinity)`.

## Discussion

Use this method to receive values on a binding you provide as the user turns the Digital Crown on Apple Watch. The example below receives changes to the binding value, starting at `0.0` and incrementing or decrementing depending on the direction that the user turns the Digital Crown:

```swift
struct DigitalCrown: View {
    @State private var crownValue = 0.0

    var body: some View {
        Text("Received Value:\(crownValue, specifier: "%.1f")")
            .focusable()
            .digitalCrownRotation($crownValue)
    }
}
```



## Interacting with the Digital Crown

- **digitalCrownAccessory(_:)**: Specifies the visibility of Digital Crown accessory Views on Apple Watch.
- **digitalCrownAccessory(content:)**: Places an accessory View next to the Digital Crown on Apple Watch.
- **digitalCrownRotation(_:from:through:sensitivity:isContinuous:isHapticFeedbackEnabled:onChange:onIdle:)**: Tracks Digital Crown rotations by updating the specified binding.
- **digitalCrownRotation(_:onChange:onIdle:)**: Tracks Digital Crown rotations by updating the specified binding.
- **digitalCrownRotation(detent:from:through:by:sensitivity:isContinuous:isHapticFeedbackEnabled:onChange:onIdle:)**: Tracks Digital Crown rotations by updating the specified binding.
- **digitalCrownRotation(_:from:through:by:sensitivity:isContinuous:isHapticFeedbackEnabled:)**: Tracks Digital Crown rotations by updating the specified binding.
- **DigitalCrownEvent**: An event emitted when the user rotates the Digital Crown.
- **DigitalCrownRotationalSensitivity**: The amount of Digital Crown rotation needed to move between two integer numbers.

