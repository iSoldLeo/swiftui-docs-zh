---
来源：https://developer.apple.com/documentation/SwiftUI/Slider/init(value:in:onEditingChanged:)
抓取时间： 2025-12-01T02:48:22Z
---

# init(value:in:onEditingChanged:)

**Initializer**

创建一个滑块，从给定范围内选择一个值。

### 声明

```swift
nonisolated init<V>(value: Binding<V>, in bounds: ClosedRange<V> = 0...1, onEditingChanged: @escaping (Bool) -> Void = { _ in }) where V : BinaryFloatingPoint, V.Stride : BinaryFloatingPoint
```

## 参数

- **value**：在 `bounds` 中选择的值。
- **bounds**：有效值的范围。默认为 `0...1`。
- **onEditingChanged**：编辑开始和结束时的回调。

## 讨论

创建实例的`value` 等于给定值在`bounds` 中的位置，映射到`0...1`。

当编辑开始和结束时，滑块会调用`onEditingChanged`。例如，在 iOS 上，当用户开始沿滑块轨道拖动拇指时，编辑就开始了。

## 创建滑块

- **init(value:in:step:onEditingChanged:)**：创建一个滑块，从给定范围内选择一个值，并按步长递增。


---
source: https://developer.apple.com/documentation/SwiftUI/Slider/init(value:in:onEditingChanged:)
crawled: 2025-12-01T02:48:22Z
---

# init(value:in:onEditingChanged:)

**Initializer**

Creates a slider to select a value from a given range.

## Declaration

```swift
nonisolated init<V>(value: Binding<V>, in bounds: ClosedRange<V> = 0...1, onEditingChanged: @escaping (Bool) -> Void = { _ in }) where V : BinaryFloatingPoint, V.Stride : BinaryFloatingPoint
```

## Parameters

- **value**: The selected value within `bounds`.
- **bounds**: The range of the valid values. Defaults to `0...1`.
- **onEditingChanged**: A callback for when editing begins and ends.

## Discussion

The `value` of the created instance is equal to the position of the given value within `bounds`, mapped into `0...1`.

The slider calls `onEditingChanged` when editing begins and ends. For example, on iOS, editing begins when the user starts to drag the thumb along the slider’s track.

## Creating a slider

- **init(value:in:step:onEditingChanged:)**: Creates a slider to select a value from a given range, subject to a step increment.

