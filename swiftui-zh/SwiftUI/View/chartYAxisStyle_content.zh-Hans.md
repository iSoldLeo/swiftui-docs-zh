--- 来源：https://developer.apple.com/documentation/SwiftUI/View/chartYAxisStyle(content:)

抓取时间：2025-12-01T10:23:11Z

---

# chartYAxisStyle(content:)

**实例方法**

配置图表的 y 轴内容。

## 声明

```swift
nonisolated func chartYAxisStyle<Content>(@ViewBuilder content: @escaping (ChartAxisContent) -> Content) -> some View where Content : View

```

## 参数

- **content**：返回坐标轴内容的闭包。

## 说明

使用此修饰符配置图表绘图区域的大小或宽高比。

例如：

```swift
Chart(data: data) {
    BarMark(x: .value("Category", $0.category))
}
.chartYAxisStyle { axis in
    axis.opacity(0.5)
}
```

## 坐标轴

- **chartXAxis(_:)**：设置 x 轴的可见性。

- **chartXAxis(content:)**：配置视图中图表的 x 轴。

- **chartXAxisStyle(content:)**：配置图表的 x 轴内容。

- **chartYAxis(_:)**：设置 y 轴的可见性。

- **chartYAxis(content:)**：配置视图中图表的 y 轴。


---
source: https://developer.apple.com/documentation/SwiftUI/View/chartYAxisStyle(content:)
crawled: 2025-12-01T10:23:11Z
---

# chartYAxisStyle(content:)

**Instance Method**

Configures the y axis content of charts.

## Declaration

```swift
nonisolated func chartYAxisStyle<Content>(@ViewBuilder content: @escaping (ChartAxisContent) -> Content) -> some View where Content : View

```

## Parameters

- **content**: A closure that returns the content of the axis.

## Discussion

Use this modifier to configure the size or aspect ratio of the plot area of charts.

For example:

```swift
Chart(data: data) {
    BarMark(x: .value("Category", $0.category))
}
.chartYAxisStyle { axis in
    axis.opacity(0.5)
}
```

## Axes

- **chartXAxis(_:)**: Sets the visibility of the x axis.
- **chartXAxis(content:)**: Configures the x-axis for charts in the view.
- **chartXAxisStyle(content:)**: Configures the x axis content of charts.
- **chartYAxis(_:)**: Sets the visibility of the y axis.
- **chartYAxis(content:)**: Configures the y-axis for charts in the view.

