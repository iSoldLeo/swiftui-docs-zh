--- 来源：https://developer.apple.com/documentation/SwiftUI/View/chartLineStyleScale(domain:range:)

抓取时间：2025-12-03T05:34:26Z

---

# chartLineStyleScale(domain:range:)

**实例方法**

配置图表的线条样式刻度。

## 声明

```swift
nonisolated func chartLineStyleScale<Domain, Range>(domain: Domain, range: Range) -> some View where Domain : ScaleDomain, Range : ScaleRange, Range.VisualValue == StrokeStyle

```

## 参数

- **domain**：图表中可绘制的线条样式数据值。对于分类值，您可以使用数组定义域（例如，`["A", "B", "C"]`）。

- **range**：与刻度域对应的线条样式范围。

## 线条样式刻度

- **chartLineStyleScale(_:)**：配置图表的线条样式刻度。

- **chartLineStyleScale(domain:)**：配置图表的线条样式刻度。

- **chartLineStyleScale(range:)**：配置图表的线条样式刻度。

- **chartLineStyleScale(domain:mapping:)**：配置图表的线条样式刻度。

- **chartLineStyleScale(mapping:)**：配置图表的线条样式刻度。


---
source: https://developer.apple.com/documentation/SwiftUI/View/chartLineStyleScale(domain:range:)
crawled: 2025-12-03T05:34:26Z
---

# chartLineStyleScale(domain:range:)

**Instance Method**

Configures the line style scale for charts.

## Declaration

```swift
nonisolated func chartLineStyleScale<Domain, Range>(domain: Domain, range: Range) -> some View where Domain : ScaleDomain, Range : ScaleRange, Range.VisualValue == StrokeStyle

```

## Parameters

- **domain**: The possible data values plotted as line styles in the chart. You can define the domain with an array for categorical values (e.g., `["A", "B", "C"]`)
- **range**: The range of line styles that correspond to the scale domain.

## Line style scales

- **chartLineStyleScale(_:)**: Configures the line style scale for charts.
- **chartLineStyleScale(domain:)**: Configures the line style scale for charts.
- **chartLineStyleScale(range:)**: Configures the line style scale for charts.
- **chartLineStyleScale(domain:mapping:)**: Configures the line style scale for charts.
- **chartLineStyleScale(mapping:)**: Configures the line style scale for charts.

