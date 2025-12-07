--- 来源：https://developer.apple.com/documentation/SwiftUI/View/digitalCrownRotation(_:from:through:by:sensitivity:isContinuous:isHapticFeedbackEnabled:)

抓取时间：2025-12-02T17:42:24Z

---

# digitalCrownRotation(_:from:through:by:sensitivity:isContinuous:isHapticFeedbackEnabled:)

**实例方法**

通过更新指定的绑定来跟踪数码表冠的旋转。

## 声明

```swift
nonisolated func digitalCrownRotation<V>(_ binding: Binding<V>, from minValue: V, through maxValue: V, by stride: V.Stride? = nil, sensitivity: DigitalCrownRotationalSensitivity = .high, isContinuous: Bool = false, isHapticFeedbackEnabled: Bool = true) -> some View where V : BinaryFloatingPoint, V.Stride : BinaryFloatingPoint

```

## 参数

- **binding**：绑定到一个值，该值会在用户旋转数码表冠时更新。

- **minValue**：报告范围的下限。

- **maxValue**：报告范围的上限。

- **stride**：该值稳定在 `stride` 的倍数上。

- **sensitivity**：用户需要旋转数码表冠多少才能在两个整数之间移动。

- **isContinuous**：控制报告的值是停止在 `minValue` 和 `maxValue` 处，还是循环。默认值为 `false`。

- **isHapticFeedbackEnabled**：控制旋转数码表冠时触觉反馈的生成。默认值为 `true`。

## 讨论

使用此方法可在用户旋转 Apple Watch 上的数码表冠时接收您提供的绑定值。以下示例接收绑定值的变化，从 `0.0` 的 `minValue` 开始，到 `10.0` 的 `maxValue` 结束，步长为 `0.1`，根据用户旋转数码表冠的方向递增或递减，如果用户超出指定的边界值，则循环：

```swift
struct DigitalCrown: View {
    @State private var crownValue = 0.0
    @State private var minValue = 0.0
    @State private var maxValue = 10.0
    @State private var stepAmount = 0.1

    var body: some View {
        Text("Received Value:\(crownValue, specifier: "%.2f")")
            .focusable()
            .digitalCrownRotation($crownValue,
                                  from: minValue,
                                  through: maxValue,
                                  by: stepAmount,
                                  sensitivity: .low,
                                  isContinuous: true)
    }
}
```

## 与数码表冠交互

- **digitalCrownAccessory(_:)**：指定 Apple Watch 上数码表冠配件视图的可见性。

- **digitalCrownAccessory(content:)**：在 Apple Watch 上的数码表冠旁边放置一个配件视图。

- **digitalCrownRotation(_:from:through:sensitivity:isContinuous:isHapticFeedbackEnabled:onChange:onIdle:)**：通过更新指定的绑定来跟踪数码表冠的旋转。

- **digitalCrownRotation(_:onChange:onIdle:)**：通过更新指定的绑定来跟踪数码表冠的旋转。

- **digitalCrownRotation(detent:from:through:by:sensitivity:isContinuous:isHapticFeedbackEnabled:onChange:onIdle:)**：通过更新指定的绑定来跟踪数码表冠的旋转。

- **digitalCrownRotation(_:)**：通过更新指定的绑定来跟踪数码表冠的旋转。

- **DigitalCrownEvent**：用户旋转数码表冠时触发的事件。

- **DigitalCrownRotationalSensitivity**：在两个整数之间移动所需的数码表冠旋转量。


---
source: https://developer.apple.com/documentation/SwiftUI/View/digitalCrownRotation(_:from:through:by:sensitivity:isContinuous:isHapticFeedbackEnabled:)
crawled: 2025-12-02T17:42:24Z
---

# digitalCrownRotation(_:from:through:by:sensitivity:isContinuous:isHapticFeedbackEnabled:)

**Instance Method**

Tracks Digital Crown rotations by updating the specified binding.

## Declaration

```swift
nonisolated func digitalCrownRotation<V>(_ binding: Binding<V>, from minValue: V, through maxValue: V, by stride: V.Stride? = nil, sensitivity: DigitalCrownRotationalSensitivity = .high, isContinuous: Bool = false, isHapticFeedbackEnabled: Bool = true) -> some View where V : BinaryFloatingPoint, V.Stride : BinaryFloatingPoint

```

## Parameters

- **binding**: A binding to a value that updates when the user rotates the  Digital Crown.
- **minValue**: Lower end of the range reported.
- **maxValue**: Upper end of the range reported.
- **stride**: The value settles on multiples of `stride`.
- **sensitivity**: How much the user needs to rotate the  Digital Crown to move between two integer numbers.
- **isContinuous**: Controls if the value reported stops at `minValue` and `maxValue`, or if it should wrap around. Default is `false`.
- **isHapticFeedbackEnabled**: Controls the generation of haptic feedback when turning the Digital Crown. Default is `true`.

## Discussion

Use this method to receive values on a binding you provides as the user turns the Digital Crown on Apple Watch. The example below receives changes to the binding value, starting at the `minValue` of  `0.0`  up to the `maxValue` of `10.0` in steps of `0.1` incrementing or decrementing depending on the direction that the user turns the Digital Crown, rolling over if the user exceeds the specified boundary values:

```swift
struct DigitalCrown: View {
    @State private var crownValue = 0.0
    @State private var minValue = 0.0
    @State private var maxValue = 10.0
    @State private var stepAmount = 0.1

    var body: some View {
        Text("Received Value:\(crownValue, specifier: "%.2f")")
            .focusable()
            .digitalCrownRotation($crownValue,
                                  from: minValue,
                                  through: maxValue,
                                  by: stepAmount,
                                  sensitivity: .low,
                                  isContinuous: true)
    }
}
```



## Interacting with the Digital Crown

- **digitalCrownAccessory(_:)**: Specifies the visibility of Digital Crown accessory Views on Apple Watch.
- **digitalCrownAccessory(content:)**: Places an accessory View next to the Digital Crown on Apple Watch.
- **digitalCrownRotation(_:from:through:sensitivity:isContinuous:isHapticFeedbackEnabled:onChange:onIdle:)**: Tracks Digital Crown rotations by updating the specified binding.
- **digitalCrownRotation(_:onChange:onIdle:)**: Tracks Digital Crown rotations by updating the specified binding.
- **digitalCrownRotation(detent:from:through:by:sensitivity:isContinuous:isHapticFeedbackEnabled:onChange:onIdle:)**: Tracks Digital Crown rotations by updating the specified binding.
- **digitalCrownRotation(_:)**: Tracks Digital Crown rotations by updating the specified binding.
- **DigitalCrownEvent**: An event emitted when the user rotates the Digital Crown.
- **DigitalCrownRotationalSensitivity**: The amount of Digital Crown rotation needed to move between two integer numbers.

