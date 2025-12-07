--- 来源：https://developer.apple.com/documentation/SwiftUI/Gauge/init(value:in:label:currentValueLabel:markedValueLabels:)

抓取时间：2025-12-03T05:41:36Z

---

# init(value:in:label:currentValueLabel:markedValueLabels:)

**Initializer**

创建一个表示指定范围内值的仪表盘。

## 声明

```swift
init<V>(value: V, in bounds: ClosedRange<V> = 0...1, @ViewBuilder label: () -> Label, @ViewBuilder currentValueLabel: () -> CurrentValueLabel, @ViewBuilder markedValueLabels: () -> MarkedValueLabels) where BoundsLabel == EmptyView, V : BinaryFloatingPoint
```

## 参数

- **value**：要在实例中显示的值。

- **bounds**：有效值的范围。默认为 `0...1`。

- **label**：描述仪表盘用途的视图。

- **currentValueLabel**：描述仪表当前值的视图。

- **markedValueLabels**：包含已标记视图的视图构建器，每个视图描述仪表的特定值。该方法会忽略此参数。

## 创建仪表

- **init(value:in:label:)**：创建一个仪表，显示指定范围内的值，并描述仪表的用途和当前值。

- **init(value:in:label:currentValueLabel:)**：创建一个仪表，显示指定范围内的值，并描述仪表的用途和当前值。

- **init(value:in:label:currentValueLabel:minimumValueLabel:maximumValueLabel:)**：创建一个仪表，显示指定范围内的值，并描述仪表的当前值、最小值和最大值。

- **init(value:in:label:currentValueLabel:minimumValueLabel:maximumValueLabel:markedValueLabels:)**：创建一个仪表，表示指定范围内的值。


---
source: https://developer.apple.com/documentation/SwiftUI/Gauge/init(value:in:label:currentValueLabel:markedValueLabels:)
crawled: 2025-12-03T05:41:36Z
---

# init(value:in:label:currentValueLabel:markedValueLabels:)

**Initializer**

Creates a gauge representing a value within a range.

## Declaration

```swift
init<V>(value: V, in bounds: ClosedRange<V> = 0...1, @ViewBuilder label: () -> Label, @ViewBuilder currentValueLabel: () -> CurrentValueLabel, @ViewBuilder markedValueLabels: () -> MarkedValueLabels) where BoundsLabel == EmptyView, V : BinaryFloatingPoint
```

## Parameters

- **value**: The value to show in the instance.
- **bounds**: The range of the valid values. Defaults to `0...1`.
- **label**: A view that describes the purpose of the gauge.
- **currentValueLabel**: A view that describes the current value of the gauge.
- **markedValueLabels**: A view builder containing tagged views, each of which describes a particular value of the gauge. The method ignores this parameter.

## Creating a gauge

- **init(value:in:label:)**: Creates a gauge showing a value within a range and describes the gauge’s purpose and current value.
- **init(value:in:label:currentValueLabel:)**: Creates a gauge showing a value within a range and that describes the gauge’s purpose and current value.
- **init(value:in:label:currentValueLabel:minimumValueLabel:maximumValueLabel:)**: Creates a gauge showing a value within a range and describes the gauge’s current, minimum, and maximum values.
- **init(value:in:label:currentValueLabel:minimumValueLabel:maximumValueLabel:markedValueLabels:)**: Creates a gauge representing a value within a range.

