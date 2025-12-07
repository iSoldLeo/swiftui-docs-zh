--- 来源：https://developer.apple.com/documentation/SwiftUI/View/chartPlotStyle(content:)

抓取时间：2025-12-03T05:33:59Z

---

# chartPlotStyle(content:)

**实例方法**

配置图表的绘图区域。

## 声明

```swift
nonisolated func chartPlotStyle<Content>(@ViewBuilder content: @escaping (ChartPlotContent) -> Content) -> some View where Content : View

```

## 参数

- **content**：返回绘图区域内容的闭包。

## 说明

使用此修饰符配置图表绘图区域的大小或宽高比。

例如：

```swift
Chart(data: data) {
    BarMark(x: .value("Category", $0.category))
}
.chartPlotStyle { content in
    content.frame(width: 100, height: 100)
}
```

## 样式

- **chartBackground(alignment:content:)**：为包含图表的视图添加背景。

- **chartForegroundStyleScale(_:)**：配置图表的前景样式比例尺。

- **chartForegroundStyleScale(domain:range:type:)**：配置图表的前景样式比例尺。

- **chartForegroundStyleScale(domain:type:)**：配置图表的前景样式比例尺。

- **chartForegroundStyleScale(domain:mapping:)**：配置图表的前景样式比例尺。

- **chartForegroundStyleScale(mapping:)**：配置图表的前景样式比例尺。

- **chartForegroundStyleScale(range:type:)**：配置图表的前景样式比例尺。

- **chartForegroundStyleScale(type:)**：配置图表的前景样式比例尺。


---
source: https://developer.apple.com/documentation/SwiftUI/View/chartPlotStyle(content:)
crawled: 2025-12-03T05:33:59Z
---

# chartPlotStyle(content:)

**Instance Method**

Configures the plot area of charts.

## Declaration

```swift
nonisolated func chartPlotStyle<Content>(@ViewBuilder content: @escaping (ChartPlotContent) -> Content) -> some View where Content : View

```

## Parameters

- **content**: A closure that returns the content of the plot area.

## Discussion

Use this modifier to configure the size or aspect ratio of the plot area of charts.

For example:

```swift
Chart(data: data) {
    BarMark(x: .value("Category", $0.category))
}
.chartPlotStyle { content in
    content.frame(width: 100, height: 100)
}
```

## Styles

- **chartBackground(alignment:content:)**: Adds a background to a view that contains a chart.
- **chartForegroundStyleScale(_:)**: Configures the foreground style scale for charts.
- **chartForegroundStyleScale(domain:range:type:)**: Configures the foreground style scale for charts.
- **chartForegroundStyleScale(domain:type:)**: Configures the foreground style scale for charts.
- **chartForegroundStyleScale(domain:mapping:)**: Configures the foreground style scale for charts.
- **chartForegroundStyleScale(mapping:)**: Configures the foreground style scale for charts.
- **chartForegroundStyleScale(range:type:)**: Configures the foreground style scale for charts.
- **chartForegroundStyleScale(type:)**: Configures the foreground style scale for charts.

