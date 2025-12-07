---
来源： https://developer.apple.com/documentation/SwiftUI/GaugeStyle/accessoryCircular
抓取时间： 2025-12-03T06:10:03Z
---

# 配件圆形

**类型属性**

一种仪表样式，显示一个打开的圆环，圆环上的某一点会出现一个标记，指示仪表的当前值。

## 声明

```swift
@MainActor @preconcurrency static var accessoryCircular: AccessoryCircularGaugeStyle { get }
```

## 讨论

使用[Gauge](../Gauge.zh-Hans.md)修饰符将此样式应用于[Gauge](../Gauge.zh-Hans.md) 或包含仪表盘的视图层次结构：

```swift
Gauge(value: batteryLevel, in: 0...100) {
    Text("Battery Level")
}
.gaugeStyle(.accessoryCircular)
```

此样式在仪表中央显示仪表的`currentValueLabel` 值。如果在创建量规时提供了`minimumValueLabel` 和`maximumValueLabel` 参数，它们将显示在环底部的开口中。否则，仪器将在该位置放置标签。

## 获取圆形量规样式

- **circular**：一种仪器样式，显示一个打开的圆环，圆环上的某一点会出现一个标记，指示仪器的当前值。
- **accessoryCircularCapacity**：一种仪表样式，显示一个部分填满的封闭环，以指示仪表的当前值。


---
source: https://developer.apple.com/documentation/SwiftUI/GaugeStyle/accessoryCircular
crawled: 2025-12-03T06:10:03Z
---

# accessoryCircular

**Type Property**

A gauge style that displays an open ring with a marker that appears at a point along the ring to indicate the gauge’s current value.

## Declaration

```swift
@MainActor @preconcurrency static var accessoryCircular: AccessoryCircularGaugeStyle { get }
```

## Discussion

Apply this style to a [Gauge](../Gauge.zh-Hans.md) or to a view hierarchy that contains gauges using the [gaugeStyle(_:)](../View/gaugeStyle.zh-Hans.md) modifier:

```swift
Gauge(value: batteryLevel, in: 0...100) {
    Text("Battery Level")
}
.gaugeStyle(.accessoryCircular)
```

This style displays the gauge’s `currentValueLabel` value at the center of the gauge. If you provide `minimumValueLabel` and `maximumValueLabel` parameters when you create the gauge, they appear in the opening at the bottom of the ring. Otherwise, the gauge places its label in that location.

## Getting circular gauge styles

- **circular**: A gauge style that displays an open ring with a marker that appears at a point along the ring to indicate the gauge’s current value.
- **accessoryCircularCapacity**: A gauge style that displays a closed ring that’s partially filled in to indicate the gauge’s current value.

