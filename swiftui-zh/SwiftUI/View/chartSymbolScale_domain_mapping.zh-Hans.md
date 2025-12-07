--- 来源：https://developer.apple.com/documentation/SwiftUI/View/chartSymbolScale(domain:mapping:)

抓取时间：2025-12-01T10:23:24Z

---

# chartSymbolScale(domain:mapping:)

**实例方法**

配置图表符号的刻度。

## 声明

```swift
nonisolated func chartSymbolScale<Domain, S>(domain: Domain, mapping: @escaping (Domain.Element) -> S) -> some View where Domain : Collection, S : ChartSymbolShape, Domain.Element : Plottable

```

## 参数

- **domain**：图表中可绘制为符号的数据值。

- **mapping**：将数据类别映射到符号形状。

## 符号刻度

- **chartSymbolScale(_:)**：配置图表符号的刻度。

- **chartSymbolScale(domain:)**：配置图表符号样式的刻度。

- **chartSymbolScale(domain:range:)**：配置图表符号样式比例。

- **chartSymbolScale(mapping:)**：配置图表符号样式比例。

- **chartSymbolScale(range:)**：配置图表符号样式比例。


---
source: https://developer.apple.com/documentation/SwiftUI/View/chartSymbolScale(domain:mapping:)
crawled: 2025-12-01T10:23:24Z
---

# chartSymbolScale(domain:mapping:)

**Instance Method**

Configures the symbol scale for charts.

## Declaration

```swift
nonisolated func chartSymbolScale<Domain, S>(domain: Domain, mapping: @escaping (Domain.Element) -> S) -> some View where Domain : Collection, S : ChartSymbolShape, Domain.Element : Plottable

```

## Parameters

- **domain**: The possible data values plotted as symbol in the chart.
- **mapping**: Maps data categories to symbol shapes.

## Symbol scales

- **chartSymbolScale(_:)**: Configures the symbol scale for charts.
- **chartSymbolScale(domain:)**: Configures the symbol style scale for charts.
- **chartSymbolScale(domain:range:)**: Configures the symbol style scale for charts.
- **chartSymbolScale(mapping:)**: Configures the symbol scale for charts.
- **chartSymbolScale(range:)**: Configures the symbol style scale for charts.

