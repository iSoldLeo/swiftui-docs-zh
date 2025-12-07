--- 来源：https://developer.apple.com/documentation/SwiftUI/Gauge/init(value:in:label:)

抓取时间：2025-12-01T10:30:45Z

---

# init(value:in:label:)

**Initializer**

创建一个仪表盘，显示指定范围内的值，并描述仪表盘的用途和当前值。

## 声明

```swift
init<V>(value: V, in bounds: ClosedRange<V> = 0...1, @ViewBuilder label: () -> Label) where CurrentValueLabel == EmptyView, BoundsLabel == EmptyView, MarkedValueLabels == EmptyView, V : BinaryFloatingPoint
```

## 参数

- **value**：仪表盘中要显示的值。

- **bounds**：有效值的范围。默认为 `0...1`。

- **label**：描述仪表盘用途的视图。

## 讨论

使用此修饰符创建一个仪表，该仪表显示其在仪表上的相对位置的值，并显示描述仪表用途的标签。在下面的示例中，仪表的范围为 `0...1`，指示器设置为 `0.4`，即沿仪表距离的 40%：

```swift
struct SimpleGauge: View {
    @State private var batteryLevel = 0.4

    var body: some View {
        Gauge(value: batteryLevel) {
            Text("Battery Level")
        }
    }
}
```

## 创建仪表

- **init(value:in:label:currentValueLabel:)**：创建一个仪表，显示指定范围内的值，并描述仪表的用途和当前值。

- **init(value:in:label:currentValueLabel:markedValueLabels:)**：创建一个仪表，表示指定范围内的值。

- **init(value:in:label:currentValueLabel:minimumValueLabel:maximumValueLabel:)**：创建一个仪表，显示指定范围内的值，并描述仪表的当前值、最小值和最大值。

- **init(value:in:label:currentValueLabel:minimumValueLabel:maximumValueLabel:markedValueLabels:)**：创建一个表示指定范围内数值的仪表盘。


---
source: https://developer.apple.com/documentation/SwiftUI/Gauge/init(value:in:label:)
crawled: 2025-12-01T10:30:45Z
---

# init(value:in:label:)

**Initializer**

Creates a gauge showing a value within a range and describes the gauge’s purpose and current value.

## Declaration

```swift
init<V>(value: V, in bounds: ClosedRange<V> = 0...1, @ViewBuilder label: () -> Label) where CurrentValueLabel == EmptyView, BoundsLabel == EmptyView, MarkedValueLabels == EmptyView, V : BinaryFloatingPoint
```

## Parameters

- **value**: The value to show in the gauge.
- **bounds**: The range of the valid values. Defaults to `0...1`.
- **label**: A view that describes the purpose of the gauge.

## Discussion

Use this modifier to create a gauge that shows the value at its relative position along the gauge and a label describing the gauge’s purpose. In the example below, the gauge has a range of `0...1`, the indicator is set to `0.4`, or 40 percent of the distance along the gauge:

```swift
struct SimpleGauge: View {
    @State private var batteryLevel = 0.4

    var body: some View {
        Gauge(value: batteryLevel) {
            Text("Battery Level")
        }
    }
}
```



## Creating a gauge

- **init(value:in:label:currentValueLabel:)**: Creates a gauge showing a value within a range and that describes the gauge’s purpose and current value.
- **init(value:in:label:currentValueLabel:markedValueLabels:)**: Creates a gauge representing a value within a range.
- **init(value:in:label:currentValueLabel:minimumValueLabel:maximumValueLabel:)**: Creates a gauge showing a value within a range and describes the gauge’s current, minimum, and maximum values.
- **init(value:in:label:currentValueLabel:minimumValueLabel:maximumValueLabel:markedValueLabels:)**: Creates a gauge representing a value within a range.

