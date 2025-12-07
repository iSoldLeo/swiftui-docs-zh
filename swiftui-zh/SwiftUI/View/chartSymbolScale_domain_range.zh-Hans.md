--- 来源：https://developer.apple.com/documentation/SwiftUI/View/chartSymbolScale(domain:range:)

抓取时间：2025-12-03T05:34:17Z

---

# chartSymbolScale(domain:range:)

**实例方法**

配置图表符号样式的刻度。

## 声明

```swift
nonisolated func chartSymbolScale<Domain, Range>(domain: Domain, range: Range) -> some View where Domain : ScaleDomain, Range : ScaleRange, Range.VisualValue : ChartSymbolShape

```

## 参数

- **domain**：图表中可绘制为符号的数据值。您可以为分类值定义一个数组作为域（例如，`["A", "B", "C"]`）。

- **range**：与刻度域对应的符号范围。

## 符号刻度

- **chartSymbolScale(_:)**：配置图表符号刻度。

- **chartSymbolScale(domain:)**：配置图表符号样式刻度。

- **chartSymbolScale(domain:mapping:)**：配置图表符号刻度。

- **chartSymbolScale(mapping:)**：配置图表符号刻度。

- **chartSymbolScale(range:)**：配置图表符号样式刻度。


---
source: https://developer.apple.com/documentation/SwiftUI/View/chartSymbolScale(domain:range:)
crawled: 2025-12-03T05:34:17Z
---

# chartSymbolScale(domain:range:)

**Instance Method**

Configures the symbol style scale for charts.

## Declaration

```swift
nonisolated func chartSymbolScale<Domain, Range>(domain: Domain, range: Range) -> some View where Domain : ScaleDomain, Range : ScaleRange, Range.VisualValue : ChartSymbolShape

```

## Parameters

- **domain**: The possible data values plotted as symbols in the chart. You can define the domain with an array for categorical values (e.g., `["A", "B", "C"]`)
- **range**: The range of symbols that correspond to the scale domain.

## Symbol scales

- **chartSymbolScale(_:)**: Configures the symbol scale for charts.
- **chartSymbolScale(domain:)**: Configures the symbol style scale for charts.
- **chartSymbolScale(domain:mapping:)**: Configures the symbol scale for charts.
- **chartSymbolScale(mapping:)**: Configures the symbol scale for charts.
- **chartSymbolScale(range:)**: Configures the symbol style scale for charts.

