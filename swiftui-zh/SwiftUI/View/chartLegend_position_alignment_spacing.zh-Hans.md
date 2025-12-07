--- 来源：https://developer.apple.com/documentation/SwiftUI/View/chartLegend(position:alignment:spacing:)

抓取时间：2025-12-03T05:34:01Z

---

# chartLegend(position:alignment:spacing:)

**实例方法**

配置图表的图例。

## 声明

```swift
@MainActor @preconcurrency func chartLegend(position: AnnotationPosition = .automatic, alignment: Alignment? = nil, spacing: CGFloat? = nil) -> some View

```

## 参数

- **position**：配置图例的位置。

- **alignment**：图例在可用空间内的对齐方式。使用 `nil` 可获得默认对齐方式。

- **spacing**：图例与图表之间的距离。使用 `nil` 可获得默认间距。

## 图例

- **chartLegend(_:)**：配置图表图例。

- **chartLegend(position:alignment:spacing:content:)**：配置图表图例。


---
source: https://developer.apple.com/documentation/SwiftUI/View/chartLegend(position:alignment:spacing:)
crawled: 2025-12-03T05:34:01Z
---

# chartLegend(position:alignment:spacing:)

**Instance Method**

Configures the legend for charts.

## Declaration

```swift
@MainActor @preconcurrency func chartLegend(position: AnnotationPosition = .automatic, alignment: Alignment? = nil, spacing: CGFloat? = nil) -> some View

```

## Parameters

- **position**: Configures the position of the legend.
- **alignment**: Alignment of the legend within the space available to it. Use `nil` for default alignment.
- **spacing**: Distance between the legend and the chart. Use `nil` for the default spacing.

## Legends

- **chartLegend(_:)**: Configures the legend for charts.
- **chartLegend(position:alignment:spacing:content:)**: Configures the legend for charts.

