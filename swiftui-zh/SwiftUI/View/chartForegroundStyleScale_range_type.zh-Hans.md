--- 来源：https://developer.apple.com/documentation/SwiftUI/View/chartForegroundStyleScale(range:type:)

抓取时间：2025-12-03T05:33:58Z

---

# chartForegroundStyleScale(range:type:)

**实例方法**

配置图表的前景样式比例。

## 声明

```swift
nonisolated func chartForegroundStyleScale<Range>(range: Range, type: ScaleType? = nil) -> some View where Range : ScaleRange, Range.VisualValue : ShapeStyle

```

## 参数

- **range**：与比例域对应的前景样式范围。

- **type**：比例类型。

## 样式

- **chartBackground(alignment:content:)**：为包含图表的视图添加背景。

- **chartForegroundStyleScale(_:)**：配置图表的前景色比例尺。

- **chartForegroundStyleScale(domain:range:type:)**：配置图表的前景色比例尺。

- **chartForegroundStyleScale(domain:type:)**：配置图表的前景色比例尺。

- **chartForegroundStyleScale(domain:mapping:)**：配置图表的前景色比例尺。

- **chartForegroundStyleScale(mapping:)**：配置图表的前景色比例尺。

- **chartForegroundStyleScale(type:)**：配置图表的前景色比例尺。

- **chartPlotStyle(content:)**：配置图表的绘图区域。


---
source: https://developer.apple.com/documentation/SwiftUI/View/chartForegroundStyleScale(range:type:)
crawled: 2025-12-03T05:33:58Z
---

# chartForegroundStyleScale(range:type:)

**Instance Method**

Configures the foreground style scale for charts.

## Declaration

```swift
nonisolated func chartForegroundStyleScale<Range>(range: Range, type: ScaleType? = nil) -> some View where Range : ScaleRange, Range.VisualValue : ShapeStyle

```

## Parameters

- **range**: The range of foreground styles that correspond to the scale domain.
- **type**: The scale type.

## Styles

- **chartBackground(alignment:content:)**: Adds a background to a view that contains a chart.
- **chartForegroundStyleScale(_:)**: Configures the foreground style scale for charts.
- **chartForegroundStyleScale(domain:range:type:)**: Configures the foreground style scale for charts.
- **chartForegroundStyleScale(domain:type:)**: Configures the foreground style scale for charts.
- **chartForegroundStyleScale(domain:mapping:)**: Configures the foreground style scale for charts.
- **chartForegroundStyleScale(mapping:)**: Configures the foreground style scale for charts.
- **chartForegroundStyleScale(type:)**: Configures the foreground style scale for charts.
- **chartPlotStyle(content:)**: Configures the plot area of charts.

