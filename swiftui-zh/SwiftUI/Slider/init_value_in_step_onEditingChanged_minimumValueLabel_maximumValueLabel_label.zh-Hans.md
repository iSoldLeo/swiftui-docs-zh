---
source: https://developer.apple.com/documentation/SwiftUI/Slider/init(value:in:step:onEditingChanged:minimumValueLabel:maximumValueLabel:label:)
抓取时间： 2025-12-01T02:48:34Z


# init(value:in:step:onEditingChanged:minimumValueLabel:maximumValueLabel:label:)

**Initializer**

创建一个滑块，用于从给定范围内选择一个值，以步长递增为条件，并显示所提供的标签。

### 声明

```swift
nonisolated init<V>(value: Binding<V>, in bounds: ClosedRange<V>, step: V.Stride = 1, onEditingChanged: @escaping (Bool) -> Void = { _ in }, minimumValueLabel: ValueLabel, maximumValueLabel: ValueLabel, @ViewBuilder label: () -> Label) where V : BinaryFloatingPoint, V.Stride : BinaryFloatingPoint
```

## 参数

- **value**：在 `bounds` 中选择的值。
- **bounds**：有效值的范围。默认为 `0...1`。
- **step**：每个有效值之间的距离。
- **onEditingChanged**：编辑开始和结束时的回调。
- **minimumValueLabel**：描述`bounds.lowerBound` 的视图。
- **maximumValueLabel**：描述`bounds.upperBound`的观点。
- **label**：描述实例用途的`View`。并非所有的滑块样式都会显示标签，但即使在这些情况下，SwiftUI 也会使用标签来实现可访问性。例如，VoiceOver 使用标签来识别滑块的用途。

##讨论

创建实例的`value` 等于给定值在`bounds` 中的位置，并映射到`0...1` 中。

当编辑开始和结束时，滑块会调用`onEditingChanged`。例如，在 iOS 上，当用户开始沿滑块轨道拖动拇指时，编辑就开始了。

## 过时的初始化程序

- **init(value:in:onEditingChanged:label:)**：创建一个滑块，从给定范围内选择一个值，并显示提供的标签。
- **init(value:in:step:onEditingChanged:label:)**：创建一个滑块，用于从给定范围内选择一个值，该值受步进增量的限制，并显示所提供的标签。
- **init(value:in:onEditingChanged:minimumValueLabel:maximumValueLabel:label:)**：创建一个滑块，从给定范围内选择一个值，并显示所提供的标签。


---
source: https://developer.apple.com/documentation/SwiftUI/Slider/init(value:in:step:onEditingChanged:minimumValueLabel:maximumValueLabel:label:)
crawled: 2025-12-01T02:48:34Z
---

# init(value:in:step:onEditingChanged:minimumValueLabel:maximumValueLabel:label:)

**Initializer**

Creates a slider to select a value from a given range, subject to a step increment, which displays the provided labels.

## Declaration

```swift
nonisolated init<V>(value: Binding<V>, in bounds: ClosedRange<V>, step: V.Stride = 1, onEditingChanged: @escaping (Bool) -> Void = { _ in }, minimumValueLabel: ValueLabel, maximumValueLabel: ValueLabel, @ViewBuilder label: () -> Label) where V : BinaryFloatingPoint, V.Stride : BinaryFloatingPoint
```

## Parameters

- **value**: The selected value within `bounds`.
- **bounds**: The range of the valid values. Defaults to `0...1`.
- **step**: The distance between each valid value.
- **onEditingChanged**: A callback for when editing begins and ends.
- **minimumValueLabel**: A view that describes `bounds.lowerBound`.
- **maximumValueLabel**: A view that describes `bounds.upperBound`.
- **label**: A `View` that describes the purpose of the instance. Not all slider styles show the label, but even in those cases, SwiftUI uses the label for accessibility. For example, VoiceOver uses the label to identify the purpose of the slider.

## Discussion

The `value` of the created instance is equal to the position of the given value within `bounds`, mapped into `0...1`.

The slider calls `onEditingChanged` when editing begins and ends. For example, on iOS, editing begins when the user starts to drag the thumb along the slider’s track.

## Deprecated initializers

- **init(value:in:onEditingChanged:label:)**: Creates a slider to select a value from a given range, which displays the provided label.
- **init(value:in:step:onEditingChanged:label:)**: Creates a slider to select a value from a given range, subject to a step increment, which displays the provided label.
- **init(value:in:onEditingChanged:minimumValueLabel:maximumValueLabel:label:)**: Creates a slider to select a value from a given range, which displays the provided labels.

