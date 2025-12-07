--- 来源：https://developer.apple.com/documentation/SwiftUI/View/chartYAxis(content:)

抓取时间：2025-12-01T10:23:10Z

---

# chartYAxis(content:)

**实例方法**

配置视图中图表的 y 轴。

## 声明

```swift
nonisolated func chartYAxis<Content>(@AxisContentBuilder content: () -> Content) -> some View where Content : AxisContent

```

## 参数

- **content**：轴的内容。

## 说明

使用此修饰符自定义图表的 y 轴。提供一个 `AxisMarks` 构建器，该构建器组合 `AxisGridLine`、`AxisTick` 和 `AxisValueLabel` 结构以形成轴。从构建器中省略组件，即可将其从生成的坐标轴中省略。例如，以下代码会向 y 轴添加网格线：

```swift
.chartYAxis {
    AxisMarks {
        AxisGridLine()
    }
}
```

使用诸如 `position:` 或 `values:` 之类的参数来控制其显示的坐标轴值的位置。

```swift
Chart(BatteryData.data, id: \.date) {
     BarMark(
         x: .value("Time", $0.date ..< $0.date.advanced(by: 1800)),
         y: .value("Battery Level", $0.level)
     )
     .foregroundStyle(.green)
 }
 .chartYAxis {
     AxisMarks(values: [0, 25, 50, 75, 100]) {
         AxisGridLine()
     }

     AxisMarks(values: [0, 50, 100]) {
         AxisValueLabel(format: Decimal.FormatStyle.Percent.percent.scale(1))
     }
 }
 .chartXAxis {
     AxisMarks(values: .stride(by: .hour, count: 3)) { value in
         if let date = value.as(Date.self) {
             let hour = Calendar.current.component(.hour, from: date)
             switch hour {
             case 0, 12:
                 AxisValueLabel {
                     VStack {
                         Text(date, format: .dateTime.hour())
                         if value.index == 0 {
                             Text(date, format: .dateTime.month().day())
                         }
                     }
                 }
             default:
                 AxisValueLabel(format: .dateTime.hour(.defaultDigits(amPM: .omitted)))
             }

             if hour == 0 {
                 AxisGridLine(stroke: StrokeStyle(lineWidth: 0.5))
                 AxisTick(stroke: StrokeStyle(lineWidth: 0.5))
             } else {
                 AxisGridLine()
                 AxisTick()
             }
         }
     }
 }
```

以上代码自定义 y 轴，使其显示在图表的前沿，并在 0% 和 100% 标记处显示实线网格线。

## 坐标轴

- **chartXAxis(_:)**：设置 x 轴的可见性。

- **chartXAxis(content:)**：配置视图中图表的 x 轴。

- **chartXAxisStyle(content:)**：配置图表的 x 轴内容。

- **chartYAxis(_:)**：设置 y 轴的可见性。

- **chartYAxisStyle(content:)**：配置图表的 y 轴内容。


---
source: https://developer.apple.com/documentation/SwiftUI/View/chartYAxis(content:)
crawled: 2025-12-01T10:23:10Z
---

# chartYAxis(content:)

**Instance Method**

Configures the y-axis for charts in the view.

## Declaration

```swift
nonisolated func chartYAxis<Content>(@AxisContentBuilder content: () -> Content) -> some View where Content : AxisContent

```

## Parameters

- **content**: The axis content.

## Discussion

Use this modifier to customize the y-axis of a chart. Provide an `AxisMarks` builder that composes `AxisGridLine`, `AxisTick`, and `AxisValueLabel` structures to form the axis. Omit components from the builder to omit them from the resulting axis. For example, the following code adds grid lines to the y-axis:

```swift
.chartYAxis {
    AxisMarks {
        AxisGridLine()
    }
}
```

Use arguments such as `position:` or `values:` to control the placement of the axis values it displays.

```swift
Chart(BatteryData.data, id: \.date) {
     BarMark(
         x: .value("Time", $0.date ..< $0.date.advanced(by: 1800)),
         y: .value("Battery Level", $0.level)
     )
     .foregroundStyle(.green)
 }
 .chartYAxis {
     AxisMarks(values: [0, 25, 50, 75, 100]) {
         AxisGridLine()
     }

     AxisMarks(values: [0, 50, 100]) {
         AxisValueLabel(format: Decimal.FormatStyle.Percent.percent.scale(1))
     }
 }
 .chartXAxis {
     AxisMarks(values: .stride(by: .hour, count: 3)) { value in
         if let date = value.as(Date.self) {
             let hour = Calendar.current.component(.hour, from: date)
             switch hour {
             case 0, 12:
                 AxisValueLabel {
                     VStack {
                         Text(date, format: .dateTime.hour())
                         if value.index == 0 {
                             Text(date, format: .dateTime.month().day())
                         }
                     }
                 }
             default:
                 AxisValueLabel(format: .dateTime.hour(.defaultDigits(amPM: .omitted)))
             }

             if hour == 0 {
                 AxisGridLine(stroke: StrokeStyle(lineWidth: 0.5))
                 AxisTick(stroke: StrokeStyle(lineWidth: 0.5))
             } else {
                 AxisGridLine()
                 AxisTick()
             }
         }
     }
 }
```



The above code customizes the y-axis to appear on the leading edge of the chart, with a solid grid line at the 0% and 100% marks.



## Axes

- **chartXAxis(_:)**: Sets the visibility of the x axis.
- **chartXAxis(content:)**: Configures the x-axis for charts in the view.
- **chartXAxisStyle(content:)**: Configures the x axis content of charts.
- **chartYAxis(_:)**: Sets the visibility of the y axis.
- **chartYAxisStyle(content:)**: Configures the y axis content of charts.

