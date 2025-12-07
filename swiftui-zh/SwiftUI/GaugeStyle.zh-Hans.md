---
来源： https://developer.apple.com/documentation/SwiftUI/GaugeStyle
抓取时间： 2025-12-02T17:33:12Z
---

# GaugeStyle

**Protocol**

定义视图层次结构中所有仪表盘实例的实现。

## 声明

```swift
@MainActor @preconcurrency protocol GaugeStyle
```

## 概览

要为视图层次结构中的所有 [Gauge](Gauge.zh-Hans.md) 实例配置样式，请使用 [gaugeStyle(_:)](View/gaugeStyle.zh-Hans.md) 修饰符。例如，您可以配置仪表使用 [circular](GaugeStyle/circular.zh-Hans.md) 样式：

```swift
Gauge(value: batteryLevel, in: 0...100) {
    Text("Battery Level")
}
.gaugeStyle(.circular)
```

如果符合该协议的类型的基本声明中包含了该协议，则该类型将继承`@preconcurrency @MainActor` 隔离：

```swift
struct MyCustomType: Transition {
    // `@preconcurrency @MainActor` isolation by default
}
```

默认情况下与主要角色隔离，但这不是必须的。在扩展声明中声明一致性，就可以不使用主要角色隔离：

```swift
extension MyCustomType: Transition {
    // `nonisolated` by default
}
```

## 获取自动样式

- **automatic**：当前样式化视图上下文中的默认 gauge 视图样式。

## 获取圆形仪表样式

- **circular**：一种仪表盘样式，显示一个打开的环，环上的某一点会出现一个标记，指示仪表盘的当前值。
- **accessoryCircular**：一种仪器样式，显示一个打开的环，环上的某一点会出现一个标记，指示仪器的当前值。
- **accessoryCircularCapacity**：一种仪表样式，显示一个部分填满的封闭环，以指示仪表的当前值。

## 获取线性仪表样式

- **linear**：一种仪表样式，显示一个条形图，在条形图的某一点上显示一个标记，以指示仪表的当前值。
- **linearCapacity**：一种仪表样式，随着仪表当前值的增加，从前缘到后缘显示填充条。
- **accessoryLinear**：一种仪表样式，显示带有标记的条形图，标记出现在条形图上的某一点，以指示仪表的当前值。
- **accessoryLinearCapacity**：一种仪表盘样式，显示条形图，随着仪表盘当前值的增加，条形图从前缘向后缘填充。

## 创建自定义仪表样式

- **makeBody(configuration:)**：创建代表仪表盘主体的视图。
- **GaugeStyle.Configuration**：量规实例的属性。
- **Body**：表示量规主体的视图。

## 支持类型

- **DefaultGaugeStyle**：当前样式化视图上下文中的默认仪表盘视图样式。
- **CircularGaugeStyle**：一种仪表盘样式，显示一个打开的环，环上的某一点会出现一个标记，指示仪表盘的当前值。
- **AccessoryCircularGaugeStyle**：一种仪器样式，显示一个打开的环，环上的某一点会出现一个标记，指示仪器的当前值。
- **AccessoryCircularCapacityGaugeStyle**：一种仪表样式，显示一个部分填满的封闭环，以指示仪表的当前值。
- **LinearGaugeStyle**：一种仪表样式，显示带有标记的条形图，标记出现在条形图上的某一点，以指示仪表的当前值。
- **LinearCapacityGaugeStyle**：一种仪表样式，随着仪表当前值的增加，从前缘到后缘显示填充条。
- **AccessoryLinearGaugeStyle**：一种仪表样式，显示带有标记的条形图，标记会出现在条形图上的某一点，以指示仪表的当前值。
- **AccessoryLinearCapacityGaugeStyle**：一种仪表盘样式，显示条形图，随着仪表盘当前值的增加，条形图从前缘向后缘填充。

### 风格指标

- **gaugeStyle(_:)**：设置此视图中仪表的样式。
- **GaugeStyleConfiguration**：仪表实例的属性。
- **progressViewStyle(_:)**：设置此视图中进度视图的样式。
- **ProgressViewStyle**：对视图层次结构中的所有进度视图应用标准交互行为的类型。
- **ProgressViewStyleConfiguration**：进度视图实例的属性。

## 符合类型

- AccessoryCircularCapacityGaugeStyle
- 附件圆形容量仪表样式
- 附件线性容量规样式
- 附件线性量规样式
- 圆形仪表样式
- 默认仪表样式
- 线性容量仪表样式
- 线性仪表样式


---
source: https://developer.apple.com/documentation/SwiftUI/GaugeStyle
crawled: 2025-12-02T17:33:12Z
---

# GaugeStyle

**Protocol**

Defines the implementation of all gauge instances within a view hierarchy.

## Declaration

```swift
@MainActor @preconcurrency protocol GaugeStyle
```

## Overview

To configure the style for all the [Gauge](Gauge.zh-Hans.md) instances in a view hierarchy, use the [gaugeStyle(_:)](View/gaugeStyle.zh-Hans.md) modifier. For example, you can configure a gauge to use the [circular](GaugeStyle/circular.zh-Hans.md) style:

```swift
Gauge(value: batteryLevel, in: 0...100) {
    Text("Battery Level")
}
.gaugeStyle(.circular)
```

A type conforming to this protocol inherits `@preconcurrency @MainActor` isolation from the protocol if the conformance is included in the type’s base declaration:

```swift
struct MyCustomType: Transition {
    // `@preconcurrency @MainActor` isolation by default
}
```

Isolation to the main actor is the default, but it’s not required. Declare the conformance in an extension to opt out of main actor isolation:

```swift
extension MyCustomType: Transition {
    // `nonisolated` by default
}
```

## Getting the automatic style

- **automatic**: The default gauge view style in the current context of the view being styled.

## Getting circular gauge styles

- **circular**: A gauge style that displays an open ring with a marker that appears at a point along the ring to indicate the gauge’s current value.
- **accessoryCircular**: A gauge style that displays an open ring with a marker that appears at a point along the ring to indicate the gauge’s current value.
- **accessoryCircularCapacity**: A gauge style that displays a closed ring that’s partially filled in to indicate the gauge’s current value.

## Getting linear gauge styles

- **linear**: A gauge style that displays a bar with a marker that appears at a point along the bar to indicate the gauge’s current value.
- **linearCapacity**: A gauge style that displays a bar that fills from leading to trailing edges as the gauge’s current value increases.
- **accessoryLinear**: A gauge style that displays bar with a marker that appears at a point along the bar to indicate the gauge’s current value.
- **accessoryLinearCapacity**: A gauge style that displays bar that fills from leading to trailing edges as the gauge’s current value increases.

## Creating custom gauge styles

- **makeBody(configuration:)**: Creates a view representing the body of a gauge.
- **GaugeStyle.Configuration**: The properties of a gauge instance.
- **Body**: A view representing the body of a gauge.

## Supporting types

- **DefaultGaugeStyle**: The default gauge view style in the current context of the view being styled.
- **CircularGaugeStyle**: A gauge style that displays an open ring with a marker that appears at a point along the ring to indicate the gauge’s current value.
- **AccessoryCircularGaugeStyle**: A gauge style that displays an open ring with a marker that appears at a point along the ring to indicate the gauge’s current value.
- **AccessoryCircularCapacityGaugeStyle**: A gauge style that displays a closed ring that’s partially filled in to indicate the gauge’s current value.
- **LinearGaugeStyle**: A gauge style that displays a bar with a marker that appears at a point along the bar to indicate the gauge’s current value.
- **LinearCapacityGaugeStyle**: A gauge style that displays bar that fills from leading to trailing edges as the gauge’s current value increases.
- **AccessoryLinearGaugeStyle**: A gauge style that displays bar with a marker that appears at a point along the bar to indicate the gauge’s current value.
- **AccessoryLinearCapacityGaugeStyle**: A gauge style that displays bar that fills from leading to trailing edges as the gauge’s current value increases.

## Styling indicators

- **gaugeStyle(_:)**: Sets the style for gauges within this view.
- **GaugeStyleConfiguration**: The properties of a gauge instance.
- **progressViewStyle(_:)**: Sets the style for progress views in this view.
- **ProgressViewStyle**: A type that applies standard interaction behavior to all progress views within a view hierarchy.
- **ProgressViewStyleConfiguration**: The properties of a progress view instance.

## Conforming Types

- AccessoryCircularCapacityGaugeStyle
- AccessoryCircularGaugeStyle
- AccessoryLinearCapacityGaugeStyle
- AccessoryLinearGaugeStyle
- CircularGaugeStyle
- DefaultGaugeStyle
- LinearCapacityGaugeStyle
- LinearGaugeStyle

