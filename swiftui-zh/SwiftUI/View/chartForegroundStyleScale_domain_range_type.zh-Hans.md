--- 来源：https://developer.apple.com/documentation/SwiftUI/View/chartForegroundStyleScale(domain:range:type:)

抓取时间：2025-12-01T10:22:58Z

---

# chartForegroundStyleScale(domain:range:type:)

**实例方法**

配置图表的前景样式比例尺。

## 声明

```swift
nonisolated func chartForegroundStyleScale<Domain, Range>(domain: Domain, range: Range, type: ScaleType? = nil) -> some View where Domain : ScaleDomain, Range : ScaleRange, Range.VisualValue : ShapeStyle

```

## 参数

- **domain**：图表中可能以前景样式绘制的数据值。您可以使用 `ClosedRange` 定义数值域，或使用 `Date` 定义类别域（例如 `0 ... 500`），也可以使用数组定义类别域（例如 `["A", "B", "C"]`）。

- **range**：与刻度域对应的前景样式范围。

- **type**：刻度类型。

## 样式

- **chartBackground(alignment:content:)**：为包含图表的视图添加背景。

- **chartForegroundStyleScale(_:)**：配置图表的前景样式刻度。

- **chartForegroundStyleScale(domain:type:)**：配置图表的前景样式刻度。

- **chartForegroundStyleScale(domain:mapping:)**：配置图表的前景色比例尺。

- **chartForegroundStyleScale(mapping:)**：配置图表的前景色比例尺。

- **chartForegroundStyleScale(range:type:)**：配置图表的前景色比例尺。

- **chartForegroundStyleScale(type:)**：配置图表的前景色比例尺。

- **chartPlotStyle(content:)**：配置图表的绘图区域。


---
source: https://developer.apple.com/documentation/SwiftUI/View/chartForegroundStyleScale(domain:range:type:)
crawled: 2025-12-01T10:22:58Z
---

# chartForegroundStyleScale(domain:range:type:)

**Instance Method**

Configures the foreground style scale for charts.

## Declaration

```swift
nonisolated func chartForegroundStyleScale<Domain, Range>(domain: Domain, range: Range, type: ScaleType? = nil) -> some View where Domain : ScaleDomain, Range : ScaleRange, Range.VisualValue : ShapeStyle

```

## Parameters

- **domain**: The possible data values plotted as foreground style in the chart. You can define the domain with a `ClosedRange` for number or `Date` values (e.g., `0 ... 500`), and with an array for categorical values (e.g., `["A", "B", "C"]`)
- **range**: The range of foreground styles that correspond to the scale domain.
- **type**: The scale type.

## Styles

- **chartBackground(alignment:content:)**: Adds a background to a view that contains a chart.
- **chartForegroundStyleScale(_:)**: Configures the foreground style scale for charts.
- **chartForegroundStyleScale(domain:type:)**: Configures the foreground style scale for charts.
- **chartForegroundStyleScale(domain:mapping:)**: Configures the foreground style scale for charts.
- **chartForegroundStyleScale(mapping:)**: Configures the foreground style scale for charts.
- **chartForegroundStyleScale(range:type:)**: Configures the foreground style scale for charts.
- **chartForegroundStyleScale(type:)**: Configures the foreground style scale for charts.
- **chartPlotStyle(content:)**: Configures the plot area of charts.

