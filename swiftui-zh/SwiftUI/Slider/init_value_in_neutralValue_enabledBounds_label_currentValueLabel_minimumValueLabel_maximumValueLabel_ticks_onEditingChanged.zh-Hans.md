---
source: https://developer.apple.com/documentation/SwiftUI/Slider/init(value:in:neutralValue:enabledBounds:label:currentValueLabel:minimumValueLabel:maximumValueLabel:ticks:onEditingChanged:)
抓取时间： 2025-12-02T21:57:50Z


# init(value:in:neutralValue:enabledBounds:label:currentValueLabel:minimumValueLabel:maximumValueLabel:ticks:onEditingChanged:)

**Initializer**

创建一个滑块，从给定范围中选择一个值，并显示提供的标签和自定义的刻度线。

### 声明

```swift
nonisolated init<V>(value: Binding<V>, in bounds: ClosedRange<V> = 0...1, neutralValue: V? = nil, enabledBounds: ClosedRange<V>? = nil, @ViewBuilder label: () -> Label, @ViewBuilder currentValueLabel: () -> some View = { EmptyView() }, @ViewBuilder minimumValueLabel: () -> ValueLabel = { EmptyView() }, @ViewBuilder maximumValueLabel: () -> ValueLabel = { EmptyView() }, @SliderTickBuilder<V> ticks: () -> some SliderTickContent, onEditingChanged: @escaping (Bool) -> Void = { _ in }) where V.Stride : BinaryFloatingPoint
```

## 参数

- **value**：在 `bounds` 中选择的值。
- **bounds**：范围值。默认为 `0...1`。
- **neutralValue**：值的起始值。
- **enabledBounds**：可选值的范围。
- **label**：描述实例用途的`View`。并非所有的滑块样式都会显示标签，但即使在这些情况下，SwiftUI 也会使用标签来实现可访问性。例如，VoiceOver 使用标签来标识滑块的用途。
- **currentValueLabel**：描述`value`的视图。
- **minimumValueLabel**：描述`bounds.lowerBound`的观点。
- **maximumValueLabel**：描述`bounds.lowerBound`的观点。
- **onEditingChanged**：编辑开始和结束时的回调。

## 讨论

创建实例的`value` 等于给定值在`bounds` 中的位置，映射到`0...1`。

当编辑开始和结束时，滑块会调用`onEditingChanged`。例如，在 iOS 上，当用户开始沿滑块轨道拖动拇指时，编辑就开始了。


---
source: https://developer.apple.com/documentation/SwiftUI/Slider/init(value:in:neutralValue:enabledBounds:label:currentValueLabel:minimumValueLabel:maximumValueLabel:ticks:onEditingChanged:)
crawled: 2025-12-02T21:57:50Z
---

# init(value:in:neutralValue:enabledBounds:label:currentValueLabel:minimumValueLabel:maximumValueLabel:ticks:onEditingChanged:)

**Initializer**

Creates a slider to select a value from a given range, which displays the provided labels and customized ticks.

## Declaration

```swift
nonisolated init<V>(value: Binding<V>, in bounds: ClosedRange<V> = 0...1, neutralValue: V? = nil, enabledBounds: ClosedRange<V>? = nil, @ViewBuilder label: () -> Label, @ViewBuilder currentValueLabel: () -> some View = { EmptyView() }, @ViewBuilder minimumValueLabel: () -> ValueLabel = { EmptyView() }, @ViewBuilder maximumValueLabel: () -> ValueLabel = { EmptyView() }, @SliderTickBuilder<V> ticks: () -> some SliderTickContent, onEditingChanged: @escaping (Bool) -> Void = { _ in }) where V.Stride : BinaryFloatingPoint
```

## Parameters

- **value**: The selected value within `bounds`.
- **bounds**: The range values. Defaults to `0...1`.
- **neutralValue**: The value’s starting value.
- **enabledBounds**: The range of selectable values.
- **label**: A `View` that describes the purpose of the instance. Not all slider styles show the label, but even in those cases, SwiftUI uses the label for accessibility. For example, VoiceOver uses the label to identify the purpose of the slider.
- **currentValueLabel**: A view that describes `value`.
- **minimumValueLabel**: A view that describes `bounds.lowerBound`.
- **maximumValueLabel**: A view that describes `bounds.lowerBound`.
- **onEditingChanged**: A callback for when editing begins and ends.

## Discussion

The `value` of the created instance is equal to the position of the given value within `bounds`, mapped into `0...1`.

The slider calls `onEditingChanged` when editing begins and ends. For example, on iOS, editing begins when the user starts to drag the thumb along the slider’s track.

