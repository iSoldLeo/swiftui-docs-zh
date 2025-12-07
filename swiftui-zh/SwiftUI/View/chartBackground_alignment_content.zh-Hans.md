--- 来源：https://developer.apple.com/documentation/SwiftUI/View/chartBackground(alignment:content:)

抓取时间：2025-12-03T05:33:53Z

---

# chartBackground(alignment:content:)

**实例方法**

为包含图表的视图添加背景。

## 声明

```swift
nonisolated func chartBackground<V>(alignment: Alignment = .center, @ViewBuilder content: @escaping (ChartProxy) -> V) -> some View where V : View

```

## 参数

- **alignment**：内容的对齐方式。

- **content**：背景的内容。

## 说明

您可以使用此修饰符将背景视图定义为视图中图表的函数。您可以使用传递给闭包的 `ChartProxy` 对象访问图表。

## 样式

- **chartForegroundStyleScale(_:)**：配置图表的前景色比例尺。

- **chartForegroundStyleScale(domain:range:type:)**：配置图表的前景色比例尺。

- **chartForegroundStyleScale(domain:type:)**：配置图表的前景色比例尺。

- **chartForegroundStyleScale(domain:mapping:)**：配置图表的前景色比例尺。

- **chartForegroundStyleScale(mapping:)**：配置图表的前景色比例尺。

- **chartForegroundStyleScale(range:type:)**：配置图表的前景色比例尺。

- **chartForegroundStyleScale(type:)**：配置图表的前景色比例尺。

- **chartPlotStyle(content:)**：配置图表的绘图区域。


---
source: https://developer.apple.com/documentation/SwiftUI/View/chartBackground(alignment:content:)
crawled: 2025-12-03T05:33:53Z
---

# chartBackground(alignment:content:)

**Instance Method**

Adds a background to a view that contains a chart.

## Declaration

```swift
nonisolated func chartBackground<V>(alignment: Alignment = .center, @ViewBuilder content: @escaping (ChartProxy) -> V) -> some View where V : View

```

## Parameters

- **alignment**: The alignment of the content.
- **content**: The content of the background.

## Discussion

You can use this modifier to define a background view as a function of the chart in the view. You can access the chart with the `ChartProxy` object passed into the closure.



## Styles

- **chartForegroundStyleScale(_:)**: Configures the foreground style scale for charts.
- **chartForegroundStyleScale(domain:range:type:)**: Configures the foreground style scale for charts.
- **chartForegroundStyleScale(domain:type:)**: Configures the foreground style scale for charts.
- **chartForegroundStyleScale(domain:mapping:)**: Configures the foreground style scale for charts.
- **chartForegroundStyleScale(mapping:)**: Configures the foreground style scale for charts.
- **chartForegroundStyleScale(range:type:)**: Configures the foreground style scale for charts.
- **chartForegroundStyleScale(type:)**: Configures the foreground style scale for charts.
- **chartPlotStyle(content:)**: Configures the plot area of charts.

