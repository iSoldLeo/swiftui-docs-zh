---
来源： https://developer.apple.com/documentation/SwiftUI/GaugeStyle/accessoryCircularCapacity
抓取时间： 2025-12-03T06:10:04Z
---

# 配件圆形容量

**类型属性**

一种量具样式，显示一个部分填充的封闭圆环，以指示量具的当前值。

## 声明

```swift
@MainActor @preconcurrency static var accessoryCircularCapacity: AccessoryCircularCapacityGaugeStyle { get }
```

## 讨论

使用[Gauge](../Gauge.zh-Hans.md)修饰符将此样式应用于[Gauge](../Gauge.zh-Hans.md) 或包含仪表的视图层次结构：

```swift
Gauge(value: batteryLevel, in: 0...100) {
    Text("Battery Level")
}
.gaugeStyle(.accessoryCircularCapacity)
```

此样式在仪表中心显示仪表的`currentValueLabel` 值。

## 获取圆形仪表样式

- **circular**：一种仪表盘样式，显示一个开放的圆环，圆环上的某一点会出现一个标记，指示仪表盘的当前值。
- **accessoryCircular**：一种仪器样式，显示一个打开的环，环上的某一点会出现一个标记，指示仪器的当前值。


---
source: https://developer.apple.com/documentation/SwiftUI/GaugeStyle/accessoryCircularCapacity
crawled: 2025-12-03T06:10:04Z
---

# accessoryCircularCapacity

**Type Property**

A gauge style that displays a closed ring that’s partially filled in to indicate the gauge’s current value.

## Declaration

```swift
@MainActor @preconcurrency static var accessoryCircularCapacity: AccessoryCircularCapacityGaugeStyle { get }
```

## Discussion

Apply this style to a [Gauge](../Gauge.zh-Hans.md) or to a view hierarchy that contains gauges using the [gaugeStyle(_:)](../View/gaugeStyle.zh-Hans.md) modifier:

```swift
Gauge(value: batteryLevel, in: 0...100) {
    Text("Battery Level")
}
.gaugeStyle(.accessoryCircularCapacity)
```

This style displays the gauge’s `currentValueLabel` value at the center of the gauge.

## Getting circular gauge styles

- **circular**: A gauge style that displays an open ring with a marker that appears at a point along the ring to indicate the gauge’s current value.
- **accessoryCircular**: A gauge style that displays an open ring with a marker that appears at a point along the ring to indicate the gauge’s current value.

