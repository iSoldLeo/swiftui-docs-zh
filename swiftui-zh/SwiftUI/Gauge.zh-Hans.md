---
来源： https://developer.apple.com/documentation/SwiftUI/Gauge
抓取时间： 2025-12-02T17:27:05Z
---

# 测量仪

**Structure**

显示某一范围内数值的视图。

## 声明

```swift
struct Gauge<Label, CurrentValueLabel, BoundsLabel, MarkedValueLabels> where Label : View, CurrentValueLabel : View, BoundsLabel : View, MarkedValueLabels : View
```

## 概览

仪表盘是一种视图，用于显示某个值的当前水平与指定的有限容量之间的关系，非常类似于汽车中的油量表。仪表显示是可配置的；它们可以显示仪表的当前值、仪表可显示的范围以及描述仪表本身用途的标签的任意组合。

在最基本的形式中，压力表显示的是沿着压力表路径映射到 0% 到 100% 范围内的单一数值。下面的示例将量规的指示器设置为量规路径上 40% 的位置：

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



您可以通过描述仪表的用途、显示其当前值及其起始值和终止值，使仪表更具描述性。本示例显示的仪表盘变体可接受量程，并使用多个尾部闭包添加标签，描述仪表盘的当前值、最小值和最大值：

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



如上图所示，仪表的默认样式是线性连续条形，带有显示当前值的指示器，以及描述仪表用途、当前值、最小值和最大值的可选标签。



要更改仪表盘的样式，请使用[gaugeStyle(_:)](View/gaugeStyle.zh-Hans.md) 视图修改器，并提供特定仪表盘样式的初始化器。例如，若要以圆形样式显示同一仪表盘，可将[circular](GaugeStyle/circular.zh-Hans.md) 样式应用于视图：

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
        .gaugeStyle(.circular)
    }
}
```



要为仪表的显示元素设计样式，可对要更改的元素应用视图修改器。在下面的示例中，当前值、最小值和最大值标签具有自定义颜色：

```swift
struct StyledGauge: View {
    @State private var current = 67.0
    @State private var minValue = 50.0
    @State private var maxValue = 170.0

    var body: some View {
        Gauge(value: current, in: minValue...maxValue) {
            Image(systemName: "heart.fill")
                .foregroundColor(.red)
        } currentValueLabel: {
            Text("\(Int(current))")
                .foregroundColor(Color.green)
        } minimumValueLabel: {
            Text("\(Int(minValue))")
                .foregroundColor(Color.green)
        } maximumValueLabel: {
            Text("\(Int(maxValue))")
                .foregroundColor(Color.red)
        }
        .gaugeStyle(.circular)
    }
}
```



您可以通过向样式的初始化器提供色调或渐变来进一步设计仪表盘的外观。下面的示例显示了在初始化[CircularGaugeStyle](CircularGaugeStyle.zh-Hans.md) 仪表时渐变的效果，即在仪表的整个长度范围内显示彩色渐变：

```swift
struct StyledGauge: View {
    @State private var current = 67.0
    @State private var minValue = 50.0
    @State private var maxValue = 170.0
    let gradient = Gradient(colors: [.green, .yellow, .orange, .red])

    var body: some View {
        Gauge(value: current, in: minValue...maxValue) {
            Image(systemName: "heart.fill")
                .foregroundColor(.red)
        } currentValueLabel: {
            Text("\(Int(current))")
                .foregroundColor(Color.green)
        } minimumValueLabel: {
            Text("\(Int(minValue))")
                .foregroundColor(Color.green)
        } maximumValueLabel: {
            Text("\(Int(maxValue))")
                .foregroundColor(Color.red)
        }
        .gaugeStyle(CircularGaugeStyle(tint: gradient))
    }
}
```



## 创建量规

- **init(value:in:label:)**：创建一个量规，显示量程内的数值，并描述量规的用途和当前值。
- **init(value:in:label:currentValueLabel:)**：创建一个量规，显示量程内的数值，并描述该量规的用途和当前值。
- **init(value:in:label:currentValueLabel:markedValueLabels:)**：创建表示量程内数值的仪表。
- **init(value:in:label:currentValueLabel:minimumValueLabel:maximumValueLabel:)**：**init(value:in:label:currentValueLabel:minimumValueLabel:maximumValueLabel:)**： 创建显示量程内数值的量规，并描述量规的当前值、最小值和最大值。
- **init(value:in:label:currentValueLabel:minimumValueLabel:maximumValueLabel:markedValueLabels:)**：创建一个量规，显示量程内的数值。

## 表示一个值

- **gaugeStyle(_:)**：设置此视图中仪表的样式。
- **ProgressView**：显示任务完成进度的视图。
- **progressViewStyle(_:)**：设置此视图中进度视图的样式。
- **DefaultDateProgressLabel**：日期相关进度视图使用当前值标签时的默认类型。
- **DefaultButtonLabel**：按钮使用的默认标签。

## 符合

- 查看


---
source: https://developer.apple.com/documentation/SwiftUI/Gauge
crawled: 2025-12-02T17:27:05Z
---

# Gauge

**Structure**

A view that shows a value within a range.

## Declaration

```swift
struct Gauge<Label, CurrentValueLabel, BoundsLabel, MarkedValueLabels> where Label : View, CurrentValueLabel : View, BoundsLabel : View, MarkedValueLabels : View
```

## Overview

A gauge is a view that shows a current level of a value in relation to a specified finite capacity, very much like a fuel gauge in an automobile. Gauge displays are configurable; they can show any combination of the gauge’s current value, the range the gauge can display, and a label describing the purpose of the gauge itself.

In its most basic form, a gauge displays a single value along the path of the gauge mapped into a range from 0 to 100 percent. The example below sets the gauge’s indicator to a position 40 percent along the gauge’s path:

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



You can make a gauge more descriptive by describing its purpose, showing its current value and its start and end values. This example shows the gauge variant that accepts a range and adds labels using multiple trailing closures describing the current value and the minimum and maximum values of the gauge:

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



As shown above, the default style for gauges is a linear, continuous bar with an indicator showing the current value, and optional labels describing the gauge’s purpose, current, minimum, and maximum values.



To change the style of a gauge, use the [gaugeStyle(_:)](View/gaugeStyle.zh-Hans.md) view modifier and supply an initializer for a specific gauge style. For example, to display the same gauge in a circular style, apply the [circular](GaugeStyle/circular.zh-Hans.md) style to the view:

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
        .gaugeStyle(.circular)
    }
}
```



To style elements of a gauge’s presentation, you apply view modifiers to the elements that you want to change. In the example below, the current value, minimum and maximum value labels have custom colors:

```swift
struct StyledGauge: View {
    @State private var current = 67.0
    @State private var minValue = 50.0
    @State private var maxValue = 170.0

    var body: some View {
        Gauge(value: current, in: minValue...maxValue) {
            Image(systemName: "heart.fill")
                .foregroundColor(.red)
        } currentValueLabel: {
            Text("\(Int(current))")
                .foregroundColor(Color.green)
        } minimumValueLabel: {
            Text("\(Int(minValue))")
                .foregroundColor(Color.green)
        } maximumValueLabel: {
            Text("\(Int(maxValue))")
                .foregroundColor(Color.red)
        }
        .gaugeStyle(.circular)
    }
}
```



You can further style a gauge’s appearance by supplying a tint color or a gradient to the style’s initializer. The following example shows the effect of a gradient in the initialization of a [CircularGaugeStyle](CircularGaugeStyle.zh-Hans.md) gauge with a colorful gradient across the length of the gauge:

```swift
struct StyledGauge: View {
    @State private var current = 67.0
    @State private var minValue = 50.0
    @State private var maxValue = 170.0
    let gradient = Gradient(colors: [.green, .yellow, .orange, .red])

    var body: some View {
        Gauge(value: current, in: minValue...maxValue) {
            Image(systemName: "heart.fill")
                .foregroundColor(.red)
        } currentValueLabel: {
            Text("\(Int(current))")
                .foregroundColor(Color.green)
        } minimumValueLabel: {
            Text("\(Int(minValue))")
                .foregroundColor(Color.green)
        } maximumValueLabel: {
            Text("\(Int(maxValue))")
                .foregroundColor(Color.red)
        }
        .gaugeStyle(CircularGaugeStyle(tint: gradient))
    }
}
```



## Creating a gauge

- **init(value:in:label:)**: Creates a gauge showing a value within a range and describes the gauge’s purpose and current value.
- **init(value:in:label:currentValueLabel:)**: Creates a gauge showing a value within a range and that describes the gauge’s purpose and current value.
- **init(value:in:label:currentValueLabel:markedValueLabels:)**: Creates a gauge representing a value within a range.
- **init(value:in:label:currentValueLabel:minimumValueLabel:maximumValueLabel:)**: Creates a gauge showing a value within a range and describes the gauge’s current, minimum, and maximum values.
- **init(value:in:label:currentValueLabel:minimumValueLabel:maximumValueLabel:markedValueLabels:)**: Creates a gauge representing a value within a range.

## Indicating a value

- **gaugeStyle(_:)**: Sets the style for gauges within this view.
- **ProgressView**: A view that shows the progress toward completion of a task.
- **progressViewStyle(_:)**: Sets the style for progress views in this view.
- **DefaultDateProgressLabel**: The default type of the current value label when used by a date-relative progress view.
- **DefaultButtonLabel**: The default label to use for a button.

## Conforms To

- View

