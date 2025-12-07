--- 来源：https://developer.apple.com/documentation/SwiftUI/View/chartSymbolScale(domain:)

抓取时间：2025-12-01T10:23:23Z

---

# chartSymbolScale(domain:)

**实例方法**

配置图表符号样式刻度。

## 声明

```swift
nonisolated func chartSymbolScale<Domain>(domain: Domain) -> some View where Domain : ScaleDomain

```

## 参数

- **domain**：图表中可绘制为符号的数据值。您可以为分类值定义一个数组作为域（例如，`["A", "B", "C"]`）。

## 符号刻度

- **chartSymbolScale(_:)**：配置图表符号刻度。

- **chartSymbolScale(domain:range:)**：配置图表符号样式刻度。

- **chartSymbolScale(domain:mapping:)**：配置图表符号刻度。

- **chartSymbolScale(mapping:)**：配置图表符号刻度。

- **chartSymbolScale(range:)**：配置图表符号样式刻度。


---
source: https://developer.apple.com/documentation/SwiftUI/View/chartSymbolScale(domain:)
crawled: 2025-12-01T10:23:23Z
---

# chartSymbolScale(domain:)

**Instance Method**

Configures the symbol style scale for charts.

## Declaration

```swift
nonisolated func chartSymbolScale<Domain>(domain: Domain) -> some View where Domain : ScaleDomain

```

## Parameters

- **domain**: The possible data values plotted as symbols in the chart. You can define the domain with an array for categorical values (e.g., `["A", "B", "C"]`)

## Symbol scales

- **chartSymbolScale(_:)**: Configures the symbol scale for charts.
- **chartSymbolScale(domain:range:)**: Configures the symbol style scale for charts.
- **chartSymbolScale(domain:mapping:)**: Configures the symbol scale for charts.
- **chartSymbolScale(mapping:)**: Configures the symbol scale for charts.
- **chartSymbolScale(range:)**: Configures the symbol style scale for charts.

