--- 来源：https://developer.apple.com/documentation/SwiftUI/View/chartLineStyleScale(domain:mapping:)

抓取时间：2025-12-01T10:23:35Z

---

# chartLineStyleScale(domain:mapping:)

**实例方法**

配置图表的线条样式比例。

## 声明

```swift
nonisolated func chartLineStyleScale<Domain>(domain: Domain, mapping: @escaping (Domain.Element) -> StrokeStyle) -> some View where Domain : Collection, Domain.Element : Plottable

```

## 参数

- **domain**：图表中可绘制的线条样式数据值。

- **mapping**：将数据类别映射到线条样式。

## 线条样式比例

- **chartLineStyleScale(_:)**：配置图表的线条样式比例。

- **chartLineStyleScale(domain:)**：配置图表的线条样式比例。

- **chartLineStyleScale(domain:range:)**：配置图表的线条样式刻度。

- **chartLineStyleScale(range:)**：配置图表的线条样式刻度。

- **chartLineStyleScale(mapping:)**：配置图表的线条样式刻度。


---
source: https://developer.apple.com/documentation/SwiftUI/View/chartLineStyleScale(domain:mapping:)
crawled: 2025-12-01T10:23:35Z
---

# chartLineStyleScale(domain:mapping:)

**Instance Method**

Configures the line style scale for charts.

## Declaration

```swift
nonisolated func chartLineStyleScale<Domain>(domain: Domain, mapping: @escaping (Domain.Element) -> StrokeStyle) -> some View where Domain : Collection, Domain.Element : Plottable

```

## Parameters

- **domain**: The possible data values plotted as line style in the chart.
- **mapping**: Maps data categories to line styles.

## Line style scales

- **chartLineStyleScale(_:)**: Configures the line style scale for charts.
- **chartLineStyleScale(domain:)**: Configures the line style scale for charts.
- **chartLineStyleScale(domain:range:)**: Configures the line style scale for charts.
- **chartLineStyleScale(range:)**: Configures the line style scale for charts.
- **chartLineStyleScale(mapping:)**: Configures the line style scale for charts.

