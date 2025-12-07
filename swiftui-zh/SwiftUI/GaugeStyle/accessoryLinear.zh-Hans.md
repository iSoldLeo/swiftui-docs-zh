---
来源： https://developer.apple.com/documentation/SwiftUI/GaugeStyle/accessoryLinear
抓取时间： 2025-12-03T06:10:06Z
---

# 配件线性

**类型属性**

一种仪表样式，用于显示带有标记的条形图，标记会出现在条形图上的某一点，以指示仪表的当前值。

### 声明

```swift
@MainActor @preconcurrency static var accessoryLinear: AccessoryLinearGaugeStyle { get }
```

## 讨论

使用[Gauge](../Gauge.zh-Hans.md)修饰符将此样式应用于[Gauge](../Gauge.zh-Hans.md) 或包含仪表盘的视图层次结构：

```swift
Gauge(value: batteryLevel, in: 0...100) {
    Text("Battery Level")
}
.gaugeStyle(.accessoryLinear)
```

如果在创建量规时提供了 `minimumValueLabel` 和 `maximumValueLabel` 参数，它们将分别显示在条形图的前缘和后缘。否则，量规将在前缘显示`currentValueLabel` 值。

## 获取线性仪表样式

- **linear**：一种仪表样式，显示一个条形图，条形图上的某一点会出现一个标记，指示仪表的当前值。
- **linearCapacity**：一种仪表样式，随着仪表当前值的增加，从前缘到后缘显示填充条。
- **accessoryLinearCapacity**：一种仪表样式，显示随着仪表当前值的增加从前缘到后缘填充的条形图。


---
source: https://developer.apple.com/documentation/SwiftUI/GaugeStyle/accessoryLinear
crawled: 2025-12-03T06:10:06Z
---

# accessoryLinear

**Type Property**

A gauge style that displays bar with a marker that appears at a point along the bar to indicate the gauge’s current value.

## Declaration

```swift
@MainActor @preconcurrency static var accessoryLinear: AccessoryLinearGaugeStyle { get }
```

## Discussion

Apply this style to a [Gauge](../Gauge.zh-Hans.md) or to a view hierarchy that contains gauges using the [gaugeStyle(_:)](../View/gaugeStyle.zh-Hans.md) modifier:

```swift
Gauge(value: batteryLevel, in: 0...100) {
    Text("Battery Level")
}
.gaugeStyle(.accessoryLinear)
```

If you provide `minimumValueLabel` and `maximumValueLabel` parameters when you create the gauge, they appear on leading and trailing edges of the bar, respectively. Otherwise, the gauge displays the `currentValueLabel` value on the leading edge.

## Getting linear gauge styles

- **linear**: A gauge style that displays a bar with a marker that appears at a point along the bar to indicate the gauge’s current value.
- **linearCapacity**: A gauge style that displays a bar that fills from leading to trailing edges as the gauge’s current value increases.
- **accessoryLinearCapacity**: A gauge style that displays bar that fills from leading to trailing edges as the gauge’s current value increases.

