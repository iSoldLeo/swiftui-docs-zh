--- 来源：https://developer.apple.com/documentation/SwiftUI/Gauge/init(value:in:label:currentValueLabel:)

抓取时间：2025-12-03T05:41:36Z

---

# init(value:in:label:currentValueLabel:)

**Initializer**

创建一个仪表盘，显示指定范围内的值，并描述仪表盘的用途和当前值。

## 声明

```swift
init<V>(value: V, in bounds: ClosedRange<V> = 0...1, @ViewBuilder label: () -> Label, @ViewBuilder currentValueLabel: () -> CurrentValueLabel) where BoundsLabel == EmptyView, MarkedValueLabels == EmptyView, V : BinaryFloatingPoint
```

## 参数

- **value**：仪表盘上显示的值。

- **bounds**：有效值的范围。默认为 `0...1`。

- **label**：描述仪表盘用途的视图。

- **currentValueLabel**：用于描述仪表当前值的视图。

## 讨论

使用此方法可以创建一个仪表，该仪表显示您提供的范围内的值，并带有描述仪表用途和当前值的标签。在下面的示例中，使用 [circular](../GaugeStyle/circular.zh-Hans.md) 样式的仪表显示其当前值 `67`，以及描述仪表 (BPM) 的标签：

```swift
struct SimpleGauge: View {
    @State private var current = 67.0

    var body: some View {
        Gauge(value: currrent, in: 0...170) {
            Text("BPM")
        } currentValueLabel: {
            Text("\(current)")
        }
        .gaugeStyle(.circular)
   }
}
```

## 创建仪表

- **init(value:in:label:)**：创建一个仪表，显示范围内的值，并描述仪表的用途和当前值。

- **init(value:in:label:currentValueLabel:markedValueLabels:)**：创建一个表示范围内值的仪表。

- **init(value:in:label:currentValueLabel:minimumValueLabel:maximumValueLabel:)**：创建一个仪表，显示指定范围内的值，并描述该仪表的当前值、最小值和最大值。

- **init(value:in:label:currentValueLabel:minimumValueLabel:maximumValueLabel:markedValueLabels:)**：创建一个仪表，表示指定范围内的值。


---
source: https://developer.apple.com/documentation/SwiftUI/Gauge/init(value:in:label:currentValueLabel:)
crawled: 2025-12-03T05:41:36Z
---

# init(value:in:label:currentValueLabel:)

**Initializer**

Creates a gauge showing a value within a range and that describes the gauge’s purpose and current value.

## Declaration

```swift
init<V>(value: V, in bounds: ClosedRange<V> = 0...1, @ViewBuilder label: () -> Label, @ViewBuilder currentValueLabel: () -> CurrentValueLabel) where BoundsLabel == EmptyView, MarkedValueLabels == EmptyView, V : BinaryFloatingPoint
```

## Parameters

- **value**: The value to show on the gauge.
- **bounds**: The range of the valid values. Defaults to `0...1`.
- **label**: A view that describes the purpose of the gauge.
- **currentValueLabel**: A view that describes the current value of the gauge.

## Discussion

Use this method to create a gauge that displays a value within a range you supply with labels that describe the purpose of the gauge and its current value. In the example below, a gauge using the [circular](../GaugeStyle/circular.zh-Hans.md) style shows its current value of `67` along with a label describing the (BPM) for the gauge:

```swift
struct SimpleGauge: View {
    @State private var current = 67.0

    var body: some View {
        Gauge(value: currrent, in: 0...170) {
            Text("BPM")
        } currentValueLabel: {
            Text("\(current)")
        }
        .gaugeStyle(.circular)
   }
}
```



## Creating a gauge

- **init(value:in:label:)**: Creates a gauge showing a value within a range and describes the gauge’s purpose and current value.
- **init(value:in:label:currentValueLabel:markedValueLabels:)**: Creates a gauge representing a value within a range.
- **init(value:in:label:currentValueLabel:minimumValueLabel:maximumValueLabel:)**: Creates a gauge showing a value within a range and describes the gauge’s current, minimum, and maximum values.
- **init(value:in:label:currentValueLabel:minimumValueLabel:maximumValueLabel:markedValueLabels:)**: Creates a gauge representing a value within a range.

