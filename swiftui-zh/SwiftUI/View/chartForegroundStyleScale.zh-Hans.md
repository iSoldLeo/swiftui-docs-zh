--- 来源：https://developer.apple.com/documentation/SwiftUI/View/chartForegroundStyleScale(_:)

抓取时间：2025-12-03T05:33:54Z

---

# chartForegroundStyleScale(_:)

**实例方法**

配置图表的前景样式比例。

## 声明

```swift
nonisolated func chartForegroundStyleScale<DataValue, S>(_ mapping: KeyValuePairs<DataValue, S>) -> some View where DataValue : Plottable, S : ShapeStyle

```

## 参数

- **mapping**：将数据类别映射到前景样式。

## 样式

- **chartBackground(alignment:content:)**：为包含图表的视图添加背景。

- **chartForegroundStyleScale(domain:range:type:)**：配置图表的前景样式比例。

- **chartForegroundStyleScale(domain:type:)**：配置图表的前景色比例尺。

- **chartForegroundStyleScale(domain:mapping:)**：配置图表的前景色比例尺。

- **chartForegroundStyleScale(mapping:)**：配置图表的前景色比例尺。

- **chartForegroundStyleScale(range:type:)**：配置图表的前景色比例尺。

- **chartForegroundStyleScale(type:)**：配置图表的前景色比例尺。

- **chartPlotStyle(content:)**：配置图表的绘图区域。


---
source: https://developer.apple.com/documentation/SwiftUI/View/chartForegroundStyleScale(_:)
crawled: 2025-12-03T05:33:54Z
---

# chartForegroundStyleScale(_:)

**Instance Method**

Configures the foreground style scale for charts.

## Declaration

```swift
nonisolated func chartForegroundStyleScale<DataValue, S>(_ mapping: KeyValuePairs<DataValue, S>) -> some View where DataValue : Plottable, S : ShapeStyle

```

## Parameters

- **mapping**: Maps data categories to foreground styles.

## Styles

- **chartBackground(alignment:content:)**: Adds a background to a view that contains a chart.
- **chartForegroundStyleScale(domain:range:type:)**: Configures the foreground style scale for charts.
- **chartForegroundStyleScale(domain:type:)**: Configures the foreground style scale for charts.
- **chartForegroundStyleScale(domain:mapping:)**: Configures the foreground style scale for charts.
- **chartForegroundStyleScale(mapping:)**: Configures the foreground style scale for charts.
- **chartForegroundStyleScale(range:type:)**: Configures the foreground style scale for charts.
- **chartForegroundStyleScale(type:)**: Configures the foreground style scale for charts.
- **chartPlotStyle(content:)**: Configures the plot area of charts.

