--- 来源：https://developer.apple.com/documentation/SwiftUI/Gauge/init(value:in:label:currentValueLabel:minimumValueLabel:maximumValueLabel:)

抓取时间：2025-12-03T05:41:37Z

---

# init(value:in:label:currentValueLabel:minimumValueLabel:maximumValueLabel:)

**Initializer**

创建一个仪表盘，显示指定范围内的值，并描述仪表盘的当前值、最小值和最大值。

## 声明

```swift
init<V>(value: V, in bounds: ClosedRange<V> = 0...1, @ViewBuilder label: () -> Label, @ViewBuilder currentValueLabel: () -> CurrentValueLabel, @ViewBuilder minimumValueLabel: () -> BoundsLabel, @ViewBuilder maximumValueLabel: () -> BoundsLabel) where MarkedValueLabels == EmptyView, V : BinaryFloatingPoint
```

## 参数

- **value**：仪表盘上显示的值。

- **bounds**：有效值的范围。默认为 `0...1`。

- **label**：描述仪表用途的视图。

- **currentValueLabel**：描述仪表当前值的视图。

- **minimumValueLabel**：描述仪表下限的视图。

- **maximumValueLabel**：描述仪表上限的视图。

## 讨论

使用此方法创建一个仪表，该仪表显示在指定范围内的值。仪表带有标签，用于描述其用途以及仪表的当前值、最小值和最大值。

```swift
struct LabeledGauge: View {
    @State private var current = 67.0
    @State private var minValue = 0.0
    @State private var maxValue = 170.0

    var body: some View {
        Gauge(value: current, in: minValue...maxValue) {
            Text("BPM")
        } currentValueLabel: {
            Text("\(Int(current))")
        } minimumValueLabel: {
            Text("\(Int(minValue))")
        } maximumValueLabel: {
            Text("\(Int(maxValue))")
        }
    }
}
```

## 创建仪表

- **init(value:in:label:)**：创建一个仪表，该仪表显示在指定范围内的值，并描述仪表的用途和当前值。

- **init(value:in:label:currentValueLabel:)**：创建一个仪表，显示指定范围内的值，并描述仪表的用途和当前值。

- **init(value:in:label:currentValueLabel:markedValueLabels:)**：创建一个仪表，表示指定范围内的值。

- **init(value:in:label:currentValueLabel:minimumValueLabel:maximumValueLabel:markedValueLabels:)**：创建一个仪表，表示指定范围内的值。


---
source: https://developer.apple.com/documentation/SwiftUI/Gauge/init(value:in:label:currentValueLabel:minimumValueLabel:maximumValueLabel:)
crawled: 2025-12-03T05:41:37Z
---

# init(value:in:label:currentValueLabel:minimumValueLabel:maximumValueLabel:)

**Initializer**

Creates a gauge showing a value within a range and describes the gauge’s current, minimum, and maximum values.

## Declaration

```swift
init<V>(value: V, in bounds: ClosedRange<V> = 0...1, @ViewBuilder label: () -> Label, @ViewBuilder currentValueLabel: () -> CurrentValueLabel, @ViewBuilder minimumValueLabel: () -> BoundsLabel, @ViewBuilder maximumValueLabel: () -> BoundsLabel) where MarkedValueLabels == EmptyView, V : BinaryFloatingPoint
```

## Parameters

- **value**: The value to show on the gauge.
- **bounds**: The range of the valid values. Defaults to `0...1`.
- **label**: A view that describes the purpose of the gauge.
- **currentValueLabel**: A view that describes the current value of the gauge.
- **minimumValueLabel**: A view that describes the lower bounds of the gauge.
- **maximumValueLabel**: A view that describes the upper bounds of the gauge.

## Discussion

Use this method to create a gauge that shows a value within a prescribed bounds. The gauge has labels that describe its purpose, and for the gauge’s current, minimum, and maximum values.

```swift
struct LabeledGauge: View {
    @State private var current = 67.0
    @State private var minValue = 0.0
    @State private var maxValue = 170.0

    var body: some View {
        Gauge(value: current, in: minValue...maxValue) {
            Text("BPM")
        } currentValueLabel: {
            Text("\(Int(current))")
        } minimumValueLabel: {
            Text("\(Int(minValue))")
        } maximumValueLabel: {
            Text("\(Int(maxValue))")
        }
    }
}
```



## Creating a gauge

- **init(value:in:label:)**: Creates a gauge showing a value within a range and describes the gauge’s purpose and current value.
- **init(value:in:label:currentValueLabel:)**: Creates a gauge showing a value within a range and that describes the gauge’s purpose and current value.
- **init(value:in:label:currentValueLabel:markedValueLabels:)**: Creates a gauge representing a value within a range.
- **init(value:in:label:currentValueLabel:minimumValueLabel:maximumValueLabel:markedValueLabels:)**: Creates a gauge representing a value within a range.

