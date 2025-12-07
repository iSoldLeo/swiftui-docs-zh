---
来源：https://developer.apple.com/documentation/SwiftUI/Slider/init(value:in:step:label:onEditingChanged:)
抓取时间： 2025-12-02T21:57:41Z


# init(value:in:step:label:onEditingChanged:)

**Initializer**

创建一个滑块，用于从给定范围内选择一个值，以步长递增为条件，并显示所提供的标签。

### 声明

```swift
nonisolated init<V>(value: Binding<V>, in bounds: ClosedRange<V>, step: V.Stride = 1, @ViewBuilder label: () -> Label, onEditingChanged: @escaping (Bool) -> Void = { _ in }) where V : BinaryFloatingPoint, V.Stride : BinaryFloatingPoint
```

## 参数

- **value**：`bounds`内的选中值。
- **bounds**：有效值的范围。
- **step**：每个有效值之间的距离。
- **label**：描述实例用途的`View`。并非所有的滑块样式都会显示标签，但即使在这些情况下，SwiftUI 也会使用标签来实现可访问性。例如，VoiceOver 使用标签来标识滑块的用途。
- **onEditingChanged**：编辑开始和结束时的回调。

## 讨论

创建实例的`value` 等于给定值在`bounds` 中的位置，映射到`0...1`。

当编辑开始和结束时，滑块会调用`onEditingChanged`。例如，在 iOS 上，当用户开始沿滑块轨道拖动拇指时，编辑就开始了。

## 创建带标签的滑块

- **init(value:in:label:onEditingChanged:)**：创建一个滑块，从给定范围内选择一个值，并显示提供的标签。
- **init(value:in:label:minimumValueLabel:maximumValueLabel:onEditingChanged:)**：创建一个滑块，从给定范围内选择一个值，并显示所提供的标签。
- **init(value:in:step:label:minimumValueLabel:maximumValueLabel:onEditingChanged:)**：创建一个滑块，用于从给定范围内选择一个值，该值受步进增量的限制，并显示所提供的标签。


---
source: https://developer.apple.com/documentation/SwiftUI/Slider/init(value:in:step:label:onEditingChanged:)
crawled: 2025-12-02T21:57:41Z
---

# init(value:in:step:label:onEditingChanged:)

**Initializer**

Creates a slider to select a value from a given range, subject to a step increment, which displays the provided label.

## Declaration

```swift
nonisolated init<V>(value: Binding<V>, in bounds: ClosedRange<V>, step: V.Stride = 1, @ViewBuilder label: () -> Label, onEditingChanged: @escaping (Bool) -> Void = { _ in }) where V : BinaryFloatingPoint, V.Stride : BinaryFloatingPoint
```

## Parameters

- **value**: The selected value within `bounds`.
- **bounds**: The range of the valid values.
- **step**: The distance between each valid value.
- **label**: A `View` that describes the purpose of the instance. Not all slider styles show the label, but even in those cases, SwiftUI uses the label for accessibility. For example, VoiceOver uses the label to identify the purpose of the slider.
- **onEditingChanged**: A callback for when editing begins and ends.

## Discussion

The `value` of the created instance is equal to the position of the given value within `bounds`, mapped into `0...1`.

The slider calls `onEditingChanged` when editing begins and ends. For example, on iOS, editing begins when the user starts to drag the thumb along the slider’s track.

## Creating a slider with labels

- **init(value:in:label:onEditingChanged:)**: Creates a slider to select a value from a given range, which displays the provided label.
- **init(value:in:label:minimumValueLabel:maximumValueLabel:onEditingChanged:)**: Creates a slider to select a value from a given range, which displays the provided labels.
- **init(value:in:step:label:minimumValueLabel:maximumValueLabel:onEditingChanged:)**: Creates a slider to select a value from a given range, subject to a step increment, which displays the provided labels.

