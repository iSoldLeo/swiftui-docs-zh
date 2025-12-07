--- 来源：https://developer.apple.com/documentation/SwiftUI/View/digitalCrownRotation(detent:from:through:by:sensitivity:isContinuous:isHapticFeedbackEnabled:onChange:onIdle:)

抓取时间：2025-12-02T17:42:22Z

---

# digitalCrownRotation(detent:from:through:by:sensitivity:isContinuous:isHapticFeedbackEnabled:onChange:onIdle:)

**实例方法**

通过更新指定的绑定来跟踪数码表冠的旋转。

## 声明

```swift
nonisolated func digitalCrownRotation<V>(detent: Binding<V>, from minValue: V, through maxValue: V, by stride: V.Stride, sensitivity: DigitalCrownRotationalSensitivity = .high, isContinuous: Bool = false, isHapticFeedbackEnabled: Bool = true, onChange: @escaping (DigitalCrownEvent) -> Void = { _ in }, onIdle: @escaping () -> Void = { }) -> some View where V : BinaryFloatingPoint, V.Stride : BinaryFloatingPoint

```

## 参数

- **detent**：一个绑定到某个值的参数，该值会在用户旋转数码表冠时更新。

- **minValue**：报告范围的下限。

- **maxValue**：报告范围的上限。

- **stride**：该值稳定在 `stride` 的倍数上。

- **sensitivity**：用户需要旋转数码表冠才能在两个定位点之间移动的幅度。

- **isContinuous**：控制报告的值是否在 `minValue` 和 `maxValue` 处停止，或者是否循环。默认值为 `false`。

- **isHapticFeedbackEnabled**：控制旋转数码表冠时触觉反馈的生成。默认值为`true`。

- **onChange**：旋转数码表冠时调用的代码块。

- **onIdle**：数码表冠静止到空闲状态时调用的代码块。

## 讨论

使用此方法可在用户旋转 Apple Watch 上的数码表冠时接收您提供的绑定值。以下示例接收绑定值的变化，从`0.0`的`minValue`开始，到`10.0`的`maxValue`为止，步长为`0.1`，根据用户旋转数码表冠的方向递增或递减，如果用户超过指定的边界值，则循环。绑定值将始终更新为所提供步长的倍数：

```swift
struct DigitalCrown: View {
    @State private var crownValue = 0.0
    @State private var selected = 0.0
    @State private var minValue = 0.0
    @State private var maxValue = 10.0
    @State private var stepAmount = 0.1
    @State private var velocity = 0.0
    @State private var isIdle = true

    var body: some View {
        Text("Received Value:\(crownValue, specifier: "%.2f")")
            .focusable()
            .digitalCrownRotation(detent: $selected,
                                  from: minValue,
                                  through: maxValue,
                                  by: stepAmount,
                                  sensitivity: .low,
                                  isContinuous: true
            ) { crownEvent in
                isIdle = false
                crownValue = crownEvent.offset
                velocity = crownEvent.velocity
            } onIdle: {
                isIdle = true
            }
    }
}
```

## 与数码表冠交互

- **digitalCrownAccessory(_:)**：指定 Apple Watch 上数码表冠配件视图的可见性。

- **digitalCrownAccessory(content:)**：在 Apple Watch 的数码表冠旁边放置一个配件视图。

- **digitalCrownRotation(_:from:through:sensitivity:isContinuous:isHapticFeedbackEnabled:onChange:onIdle:)**：通过更新指定的绑定值来跟踪数码表冠的旋转。

- **digitalCrownRotation(_:onChange:onIdle:)**：通过更新指定的绑定值来跟踪数码表冠的旋转。

- **digitalCrownRotation(_:)**：通过更新指定的绑定值来跟踪数码表冠的旋转。

- **digitalCrownRotation(_:from:through:by:sensitivity:isContinuous:isHapticFeedbackEnabled:)**：通过更新指定的绑定值来跟踪数码表冠的旋转。

- **DigitalCrownEvent**：用户旋转数码表冠时触发的事件。

- **DigitalCrownRotationalSensitivity**：在两个整数之间移动所需的数码表冠旋转角度。


---
source: https://developer.apple.com/documentation/SwiftUI/View/digitalCrownRotation(detent:from:through:by:sensitivity:isContinuous:isHapticFeedbackEnabled:onChange:onIdle:)
crawled: 2025-12-02T17:42:22Z
---

# digitalCrownRotation(detent:from:through:by:sensitivity:isContinuous:isHapticFeedbackEnabled:onChange:onIdle:)

**Instance Method**

Tracks Digital Crown rotations by updating the specified binding.

## Declaration

```swift
nonisolated func digitalCrownRotation<V>(detent: Binding<V>, from minValue: V, through maxValue: V, by stride: V.Stride, sensitivity: DigitalCrownRotationalSensitivity = .high, isContinuous: Bool = false, isHapticFeedbackEnabled: Bool = true, onChange: @escaping (DigitalCrownEvent) -> Void = { _ in }, onIdle: @escaping () -> Void = { }) -> some View where V : BinaryFloatingPoint, V.Stride : BinaryFloatingPoint

```

## Parameters

- **detent**: A binding to a value that updates when the user rotates the  Digital Crown.
- **minValue**: Lower end of the range reported.
- **maxValue**: Upper end of the range reported.
- **stride**: The value settles on multiples of `stride`.
- **sensitivity**: How much the user needs to rotate the  Digital Crown to move between two detents.
- **isContinuous**: Controls if the value reported stops at `minValue` and `maxValue`, or if it should wrap around. Default is `false`.
- **isHapticFeedbackEnabled**: Controls the generation of haptic feedback when turning the Digital Crown. Default is `true`.
- **onChange**: A block that is called as the Digital Crown is rotated.
- **onIdle**: A block that is called when the Digital Crown has settled to an idle state.

## Discussion

Use this method to receive values on a binding you provide as the user turns the Digital Crown on Apple Watch. The example below receives changes to the binding value, starting at the `minValue` of  `0.0`  up to the `maxValue` of `10.0` in steps of `0.1` incrementing or decrementing depending on the direction that the user turns the Digital Crown, rolling over if the user exceeds the specified boundary values. The binding will always be updated to a value that is a multiple of the stride that is provided:

```swift
struct DigitalCrown: View {
    @State private var crownValue = 0.0
    @State private var selected = 0.0
    @State private var minValue = 0.0
    @State private var maxValue = 10.0
    @State private var stepAmount = 0.1
    @State private var velocity = 0.0
    @State private var isIdle = true

    var body: some View {
        Text("Received Value:\(crownValue, specifier: "%.2f")")
            .focusable()
            .digitalCrownRotation(detent: $selected,
                                  from: minValue,
                                  through: maxValue,
                                  by: stepAmount,
                                  sensitivity: .low,
                                  isContinuous: true
            ) { crownEvent in
                isIdle = false
                crownValue = crownEvent.offset
                velocity = crownEvent.velocity
            } onIdle: {
                isIdle = true
            }
    }
}
```



## Interacting with the Digital Crown

- **digitalCrownAccessory(_:)**: Specifies the visibility of Digital Crown accessory Views on Apple Watch.
- **digitalCrownAccessory(content:)**: Places an accessory View next to the Digital Crown on Apple Watch.
- **digitalCrownRotation(_:from:through:sensitivity:isContinuous:isHapticFeedbackEnabled:onChange:onIdle:)**: Tracks Digital Crown rotations by updating the specified binding.
- **digitalCrownRotation(_:onChange:onIdle:)**: Tracks Digital Crown rotations by updating the specified binding.
- **digitalCrownRotation(_:)**: Tracks Digital Crown rotations by updating the specified binding.
- **digitalCrownRotation(_:from:through:by:sensitivity:isContinuous:isHapticFeedbackEnabled:)**: Tracks Digital Crown rotations by updating the specified binding.
- **DigitalCrownEvent**: An event emitted when the user rotates the Digital Crown.
- **DigitalCrownRotationalSensitivity**: The amount of Digital Crown rotation needed to move between two integer numbers.

