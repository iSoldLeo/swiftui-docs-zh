--- 来源：https://developer.apple.com/documentation/SwiftUI/View/chartLegend(position:alignment:spacing:content:)

抓取时间：2025-12-01T10:23:05Z

---

# chartLegend(position:alignment:spacing:content:)

**实例方法**

配置图表的图例。

## 声明

```swift
nonisolated func chartLegend<Content>(position: AnnotationPosition = .automatic, alignment: Alignment? = nil, spacing: CGFloat? = nil, @ViewBuilder content: () -> Content) -> some View where Content : View

```

## 参数

- **position**：配置图例的位置。

- **alignment**：图例在可用空间内的对齐方式。使用 `nil` 可获得默认对齐方式。

- **spacing**：图例与图表之间的距离。使用 `nil` 可设置默认间距。

- **content**：图例内容。

## 图例

- **chartLegend(_:)**：配置图表图例。

- **chartLegend(position:alignment:spacing:)**：配置图表图例。


---
source: https://developer.apple.com/documentation/SwiftUI/View/chartLegend(position:alignment:spacing:content:)
crawled: 2025-12-01T10:23:05Z
---

# chartLegend(position:alignment:spacing:content:)

**Instance Method**

Configures the legend for charts.

## Declaration

```swift
nonisolated func chartLegend<Content>(position: AnnotationPosition = .automatic, alignment: Alignment? = nil, spacing: CGFloat? = nil, @ViewBuilder content: () -> Content) -> some View where Content : View

```

## Parameters

- **position**: Configures the position of the legend.
- **alignment**: Alignment of the legend within the space available to it. Use `nil` for default alignment.
- **spacing**: Distance between the legend and the chart. Use `nil` for the default spacing.
- **content**: The content of the legend.

## Legends

- **chartLegend(_:)**: Configures the legend for charts.
- **chartLegend(position:alignment:spacing:)**: Configures the legend for charts.

