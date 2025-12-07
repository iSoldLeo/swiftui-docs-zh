--- 来源：https://developer.apple.com/documentation/SwiftUI/View/chartXAxis(content:)

抓取时间：2025-12-01T10:23:08Z

---

# chartXAxis(content:)

**实例方法**

配置视图中图表的 x 轴。

## 声明

```swift
nonisolated func chartXAxis<Content>(@AxisContentBuilder content: () -> Content) -> some View where Content : AxisContent

```

## 参数

- **content**：轴的内容。

## 说明

使用此修饰符自定义图表的 x 轴。提供一个 `AxisMarks` 构建器，该构建器组合 `AxisGridLine`、`AxisTick` 和 `AxisValueLabel` 结构以形成轴。从构建器中省略组件，即可将其从生成的坐标轴中省略。例如，以下代码会向 x 轴添加网格线：

```swift
.chartXAxis {
    AxisMarks {
        AxisGridLine()
    }
}
```

您还可以组合多个 `AxisMarks` 来创建更复杂的坐标轴：

```swift
Chart(BatteryData.data, id: \.date) {
     BarMark(
         x: .value("Time", $0.date ..< $0.date.advanced(by: 1800)),
         y: .value("Battery Level", $0.level)
     )
     .foregroundStyle(.green)
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
 .chartYAxis {
     AxisMarks(values: [0, 25, 50, 75, 100]) {
         AxisGridLine()
     }

     AxisMarks(values: [0, 50, 100]) {
         AxisValueLabel(format: Decimal.FormatStyle.Percent.percent.scale(1))
     }
 }
```

上面的示例使用两个 `AxisMarks` 声明自定义 x 轴。第一个声明为一天中的每个小时创建一条网格线。第二个声明为一天中每六个小时添加一个刻度和标签，并在坐标轴的起始位置添加第二行显示日期。

## 坐标轴

- **chartXAxis(_:)**：设置 x 轴的可见性。

- **chartXAxisStyle(content:)**：配置图表的 x 轴内容。

- **chartYAxis(_:)**：设置 y 轴的可见性。

- **chartYAxis(content:)**：配置视图中图表的 y 轴。

- **chartYAxisStyle(content:)**：配置图表的 y 轴内容。


---
source: https://developer.apple.com/documentation/SwiftUI/View/chartXAxis(content:)
crawled: 2025-12-01T10:23:08Z
---

# chartXAxis(content:)

**Instance Method**

Configures the x-axis for charts in the view.

## Declaration

```swift
nonisolated func chartXAxis<Content>(@AxisContentBuilder content: () -> Content) -> some View where Content : AxisContent

```

## Parameters

- **content**: The axis content.

## Discussion

Use this modifier to customize the x-axis of a chart. Provide an `AxisMarks` builder that composes `AxisGridLine`, `AxisTick`, and `AxisValueLabel` structures to form the axis. Omit components from the builder to omit them from the resulting axis. For example, the following code adds grid lines to the x-axis:

```swift
.chartXAxis {
    AxisMarks {
        AxisGridLine()
    }
}
```

You can also compose multiple `AxisMarks` to create more complex axes:

```swift
Chart(BatteryData.data, id: \.date) {
     BarMark(
         x: .value("Time", $0.date ..< $0.date.advanced(by: 1800)),
         y: .value("Battery Level", $0.level)
     )
     .foregroundStyle(.green)
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
 .chartYAxis {
     AxisMarks(values: [0, 25, 50, 75, 100]) {
         AxisGridLine()
     }

     AxisMarks(values: [0, 50, 100]) {
         AxisValueLabel(format: Decimal.FormatStyle.Percent.percent.scale(1))
     }
 }
```



The above example above customizes the x-axis using two `AxisMarks` declarations. The first creates a grid line for every hour in the day. The second adds a tick and label for every six hours in the day, with a second line showing the date for the very beginning of the axis.



## Axes

- **chartXAxis(_:)**: Sets the visibility of the x axis.
- **chartXAxisStyle(content:)**: Configures the x axis content of charts.
- **chartYAxis(_:)**: Sets the visibility of the y axis.
- **chartYAxis(content:)**: Configures the y-axis for charts in the view.
- **chartYAxisStyle(content:)**: Configures the y axis content of charts.

