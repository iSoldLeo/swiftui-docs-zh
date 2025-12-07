--- 来源：https://developer.apple.com/documentation/SwiftUI/View/chartForegroundStyleScale(domain:mapping:)

抓取时间：2025-12-03T05:33:56Z

---

# chartForegroundStyleScale(domain:mapping:)

**实例方法**

配置图表的前景样式比例。

## 声明

```swift
nonisolated func chartForegroundStyleScale<Domain, S>(domain: Domain, mapping: @escaping (Domain.Element) -> S) -> some View where Domain : Collection, S : ShapeStyle, Domain.Element : Plottable

```

## 参数

- **domain**：图表中可能以前景样式绘制的数据值。

- **mapping**：将数据类别映射到前景样式。

## 样式

- **chartBackground(alignment:content:)**：为包含图表的视图添加背景。

- **chartForegroundStyleScale(_:)**：配置图表的前景色比例尺。

- **chartForegroundStyleScale(domain:range:type:)**：配置图表的前景色比例尺。

- **chartForegroundStyleScale(domain:type:)**：配置图表的前景色比例尺。

- **chartForegroundStyleScale(mapping:)**：配置图表的前景色比例尺。

- **chartForegroundStyleScale(range:type:)**：配置图表的前景色比例尺。

- **chartForegroundStyleScale(type:)**：配置图表的前景色比例尺。

- **chartPlotStyle(content:)**：配置图表的绘图区域。


---
source: https://developer.apple.com/documentation/SwiftUI/View/chartForegroundStyleScale(domain:mapping:)
crawled: 2025-12-03T05:33:56Z
---

# chartForegroundStyleScale(domain:mapping:)

**Instance Method**

Configures the foreground style scale for charts.

## Declaration

```swift
nonisolated func chartForegroundStyleScale<Domain, S>(domain: Domain, mapping: @escaping (Domain.Element) -> S) -> some View where Domain : Collection, S : ShapeStyle, Domain.Element : Plottable

```

## Parameters

- **domain**: The possible data values plotted as foreground style in the chart.
- **mapping**: Maps data categories to foreground styles.

## Styles

- **chartBackground(alignment:content:)**: Adds a background to a view that contains a chart.
- **chartForegroundStyleScale(_:)**: Configures the foreground style scale for charts.
- **chartForegroundStyleScale(domain:range:type:)**: Configures the foreground style scale for charts.
- **chartForegroundStyleScale(domain:type:)**: Configures the foreground style scale for charts.
- **chartForegroundStyleScale(mapping:)**: Configures the foreground style scale for charts.
- **chartForegroundStyleScale(range:type:)**: Configures the foreground style scale for charts.
- **chartForegroundStyleScale(type:)**: Configures the foreground style scale for charts.
- **chartPlotStyle(content:)**: Configures the plot area of charts.

