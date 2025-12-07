---
来源： https://developer.apple.com/documentation/SwiftUI/View-Chart-View
抓取时间： 2025-12-02T17:22:12Z
---

# 图表视图修改器

**API 集合**

配置使用 Swift 图表声明的图表。

## 概览

使用这些修改器可配置添加到 SwiftUI 应用程序中的[doc://com.apple.documentation/documentation/Charts/Chart] 视图。

## 样式

- **chartBackground(alignment:content:)**：为包含图表的视图添加背景。
- **chartForegroundStyleScale(_:)**：配置图表的前景样式比例。
- **chartForegroundStyleScale(domain:range:type:)**：配置图表的前景样式比例。
- **chartForegroundStyleScale(domain:type:)**：配置图表的前景样式比例。
- **chartForegroundStyleScale(domain:mapping:)**： 配置图表的前景样式比例：配置图表的前景样式比例。
- **chartForegroundStyleScale(mapping:)**：配置图表的前景样式比例。
- **chartForegroundStyleScale(range:type:)**：配置图表的前景样式比例。
- **chartForegroundStyleScale(type:)**：配置图表的前景样式比例。
- **chartPlotStyle(content:)**： 配置图表的前景样式比例：配置图表的绘图区域。

## 图例

- **chartLegend(_:)**：配置图表的图例。
- **chartLegend(position:alignment:spacing:)**: 配置图表的图例：配置图表的图例。
- **chartLegend(position:alignment:spacing:content:)**： 配置图表的图例：配置图表的图例。

## 叠加

- **chartOverlay(alignment:content:)**：为包含图表的视图添加覆盖图。

## 轴

- **chartXAxis(_:)**：设置 x 轴的可见性。
- **chartXAxis(content:)**：为视图中的图表配置 x 轴。
- **chartXAxisStyle(content:)**：配置图表的 x 轴内容。
- **chartYAxis(_:)**：设置 Y 轴的可见性。
- **chartYAxis(content:)**：为视图中的图表配置 y 轴。
- **chartYAxisStyle(content:)**：配置图表的 Y 轴内容。

## 轴标签

- **chartXAxisLabel(_:position:alignment:spacing:)**：为视图中的图表添加 x 轴标签。
- **chartXAxisLabel(position:alignment:spacing:content:)**：为视图中的图表添加 x 轴标签。
- **chartYAxisLabel(_:position:alignment:spacing:)**：为视图中的图表添加 y 轴标签。
- **chartYAxisLabel(position:alignment:spacing:content:)**：为视图中的图表添加 y 轴标签。

## 轴刻度

- **chartXScale(domain:range:type:)**：配置图表的 x 比例。
- **chartXScale(domain:type:)**：配置图表的 x 比例。
- **chartXScale(range:type:)**：配置图表的 x 比例。
- **chartXScale(type:)**：配置图表的 x 比例。
- **chartYScale(domain:range:type:)**：配置图表的 y 比例。
- **chartYScale(domain:type:)**：配置图表的 Y 比例。
- **chartYScale(range:type:)**：配置图表的 Y 比例。
- **chartYScale(type:)**：配置图表的 Y 比例。

## 符号标度

- **chartSymbolScale(_:)**：配置图表的符号比例。
- **chartSymbolScale(domain:)**：配置图表的符号样式比例。
- **chartSymbolScale(domain:range:)**： 配置图表的符号样式比例：配置图表的符号样式比例。
- **chartSymbolScale(domain:mapping:)**：配置图表的符号比例。
- **chartSymbolScale(mapping:)**：配置图表的符号比例。
- **chartSymbolScale(range:)**：配置图表的符号样式比例。

## 符号大小比例

- **chartSymbolSizeScale(_:)**：配置图表的符号大小比例。
- **chartSymbolSizeScale(domain:range:type:)**：配置图表的符号大小比例。
- **chartSymbolSizeScale(domain:type:)**：配置图表的符号大小比例。
- **chartSymbolSizeScale(domain:mapping:)**：配置图表的符号大小比例。
- **chartSymbolSizeScale(mapping:)**：配置图表的符号大小比例。
- **chartSymbolSizeScale(range:type:)**：配置图表的符号大小比例。
- **chartSymbolSizeScale(type:)**：配置图表的符号大小比例。

## 线条样式标尺

- **chartLineStyleScale(_:)**：配置图表的线条样式比例。
- **chartLineStyleScale(domain:)**：配置图表的线条样式比例。
- **chartLineStyleScale(domain:range:)**：配置图表的线条样式比例。
- **chartLineStyleScale(range:)**：配置图表的线条样式比例。
- **chartLineStyleScale(domain:mapping:)**：配置图表的线条样式比例。
- **chartLineStyleScale(mapping:)**： 配置图表的线条样式比例：配置图表的线条样式比例。

## 滚动

- **chartScrollPosition(initialX:)**：设置沿 x 轴的初始滚动位置。一旦用户滚动了滚动视图，为该修改器提供的值将不起作用。
- **chartScrollPosition(initialY:)**：设置沿 Y 轴的初始滚动位置。一旦用户滚动了滚动视图，为该修改器提供的值将不起作用。
- **chartScrollPosition(x:)**：当图表沿 x 轴滚动时，关联要更新的绑定。
- **chartScrollPosition(y:)**：当图表沿 Y 轴滚动时，关联要更新的绑定。
- **chartScrollTargetBehavior(_:)**：设置可滚动图表的滚动行为。
- **chartScrollableAxes(_:)**：配置此视图中图表的滚动行为。

### 选择

- **chartXSelection(range:)**
- **chartXSelection(value:)**
- **chartYSelection(range:)**
- **chartYSelection(value:)**
- **chartAngleSelection(value:)**

## 可见域

- **chartXVisibleDomain(length:)**：设置 X 维可见域的长度。
- **chartYVisibleDomain(length:)**：设置可见域在 Y 维的长度。

##交互作用

- **chartGesture(_:)**：设置可见域在 Y 维的长度。

## 配置视图元素

- **可访问性修改器**：让每个人（包括残障人士）都能访问您的 SwiftUI 应用程序。
- 外观修改器***：配置视图的前景和背景样式、控件和可见性。
- 文本和符号修改器**：管理视图中文本的渲染、选择和输入。
- 辅助视图修改器**：添加和配置辅助视图，如工具栏和上下文菜单。


---
source: https://developer.apple.com/documentation/SwiftUI/View-Chart-View
crawled: 2025-12-02T17:22:12Z
---

# Chart view modifiers

**API Collection**

Configure charts that you declare with Swift Charts.

## Overview

Use these modifiers to configure a [doc://com.apple.documentation/documentation/Charts/Chart] view that you add to your SwiftUI app.

## Styles

- **chartBackground(alignment:content:)**: Adds a background to a view that contains a chart.
- **chartForegroundStyleScale(_:)**: Configures the foreground style scale for charts.
- **chartForegroundStyleScale(domain:range:type:)**: Configures the foreground style scale for charts.
- **chartForegroundStyleScale(domain:type:)**: Configures the foreground style scale for charts.
- **chartForegroundStyleScale(domain:mapping:)**: Configures the foreground style scale for charts.
- **chartForegroundStyleScale(mapping:)**: Configures the foreground style scale for charts.
- **chartForegroundStyleScale(range:type:)**: Configures the foreground style scale for charts.
- **chartForegroundStyleScale(type:)**: Configures the foreground style scale for charts.
- **chartPlotStyle(content:)**: Configures the plot area of charts.

## Legends

- **chartLegend(_:)**: Configures the legend for charts.
- **chartLegend(position:alignment:spacing:)**: Configures the legend for charts.
- **chartLegend(position:alignment:spacing:content:)**: Configures the legend for charts.

## Overlays

- **chartOverlay(alignment:content:)**: Adds an overlay to a view that contains a chart.

## Axes

- **chartXAxis(_:)**: Sets the visibility of the x axis.
- **chartXAxis(content:)**: Configures the x-axis for charts in the view.
- **chartXAxisStyle(content:)**: Configures the x axis content of charts.
- **chartYAxis(_:)**: Sets the visibility of the y axis.
- **chartYAxis(content:)**: Configures the y-axis for charts in the view.
- **chartYAxisStyle(content:)**: Configures the y axis content of charts.

## Axis Labels

- **chartXAxisLabel(_:position:alignment:spacing:)**: Adds x axis label for charts in the view.
- **chartXAxisLabel(position:alignment:spacing:content:)**: Adds x axis label for charts in the view.
- **chartYAxisLabel(_:position:alignment:spacing:)**: Adds y axis label for charts in the view.
- **chartYAxisLabel(position:alignment:spacing:content:)**: Adds y axis label for charts in the view.

## Axis scales

- **chartXScale(domain:range:type:)**: Configures the x scale for charts.
- **chartXScale(domain:type:)**: Configures the x scale for charts.
- **chartXScale(range:type:)**: Configures the x scale for charts.
- **chartXScale(type:)**: Configures the x scale for charts.
- **chartYScale(domain:range:type:)**: Configures the y scale for charts.
- **chartYScale(domain:type:)**: Configures the y scale for charts.
- **chartYScale(range:type:)**: Configures the y scale for charts.
- **chartYScale(type:)**: Configures the y scale for charts.

## Symbol scales

- **chartSymbolScale(_:)**: Configures the symbol scale for charts.
- **chartSymbolScale(domain:)**: Configures the symbol style scale for charts.
- **chartSymbolScale(domain:range:)**: Configures the symbol style scale for charts.
- **chartSymbolScale(domain:mapping:)**: Configures the symbol scale for charts.
- **chartSymbolScale(mapping:)**: Configures the symbol scale for charts.
- **chartSymbolScale(range:)**: Configures the symbol style scale for charts.

## Symbol size scales

- **chartSymbolSizeScale(_:)**: Configures the symbol size scale for charts.
- **chartSymbolSizeScale(domain:range:type:)**: Configures the symbol size scale for charts.
- **chartSymbolSizeScale(domain:type:)**: Configures the symbol size scale for charts.
- **chartSymbolSizeScale(domain:mapping:)**: Configures the symbol size scale for charts.
- **chartSymbolSizeScale(mapping:)**: Configures the symbol size scale for charts.
- **chartSymbolSizeScale(range:type:)**: Configures the symbol size scale for charts.
- **chartSymbolSizeScale(type:)**: Configures the symbol size scale for charts.

## Line style scales

- **chartLineStyleScale(_:)**: Configures the line style scale for charts.
- **chartLineStyleScale(domain:)**: Configures the line style scale for charts.
- **chartLineStyleScale(domain:range:)**: Configures the line style scale for charts.
- **chartLineStyleScale(range:)**: Configures the line style scale for charts.
- **chartLineStyleScale(domain:mapping:)**: Configures the line style scale for charts.
- **chartLineStyleScale(mapping:)**: Configures the line style scale for charts.

## Scrolling

- **chartScrollPosition(initialX:)**: Sets the initial scroll position along the x-axis. Once the user scrolls the scroll view, the value provided to this modifier will have no effect.
- **chartScrollPosition(initialY:)**: Sets the initial scroll position along the y-axis. Once the user scrolls the scroll view, the value provided to this modifier will have no effect.
- **chartScrollPosition(x:)**: Associates a binding to be updated when the chart scrolls along the x-axis.
- **chartScrollPosition(y:)**: Associates a binding to be updated when the chart scrolls along the y-axis.
- **chartScrollTargetBehavior(_:)**: Sets the scroll behavior of the scrollable chart.
- **chartScrollableAxes(_:)**: Configures the scrollable behavior of charts in this view.

## Selection

- **chartXSelection(range:)**
- **chartXSelection(value:)**
- **chartYSelection(range:)**
- **chartYSelection(value:)**
- **chartAngleSelection(value:)**

## Visible domain

- **chartXVisibleDomain(length:)**: Sets the length of the visible domain in the X dimension.
- **chartYVisibleDomain(length:)**: Sets the length of the visible domain in the Y dimension.

## Interaction

- **chartGesture(_:)**

## Configuring view elements

- **Accessibility modifiers**: Make your SwiftUI apps accessible to everyone, including people with disabilities.
- **Appearance modifiers**: Configure a view’s foreground and background styles, controls, and visibility.
- **Text and symbol modifiers**: Manage the rendering, selection, and entry of text in your view.
- **Auxiliary view modifiers**: Add and configure supporting views, like toolbars and context menus.

