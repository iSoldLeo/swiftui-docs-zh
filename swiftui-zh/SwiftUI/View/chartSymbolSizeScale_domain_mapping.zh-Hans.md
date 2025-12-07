--- 来源：https://developer.apple.com/documentation/SwiftUI/View/chartSymbolSizeScale(domain:mapping:)

抓取时间：2025-12-03T05:34:22Z

---

# chartSymbolSizeScale(domain:mapping:)

**实例方法**

配置图表符号大小刻度。

## 声明

```swift
nonisolated func chartSymbolSizeScale<Domain>(domain: Domain, mapping: @escaping (Domain.Element) -> CGFloat) -> some View where Domain : Collection, Domain.Element : Plottable

```

## 参数

- **domain**：图表中可绘制为符号大小的数据值。

- **mapping**：将数据类别映射到符号大小。

## 符号大小刻度

- **chartSymbolSizeScale(_:)**：配置图表符号大小刻度。

- **chartSymbolSizeScale(domain:range:type:)**：配置图表符号大小比例。

- **chartSymbolSizeScale(domain:type:)**：配置图表符号大小比例。

- **chartSymbolSizeScale(mapping:)**：配置图表符号大小比例。

- **chartSymbolSizeScale(range:type:)**：配置图表符号大小比例。

- **chartSymbolSizeScale(type:)**：配置图表符号大小比例。


---
source: https://developer.apple.com/documentation/SwiftUI/View/chartSymbolSizeScale(domain:mapping:)
crawled: 2025-12-03T05:34:22Z
---

# chartSymbolSizeScale(domain:mapping:)

**Instance Method**

Configures the symbol size scale for charts.

## Declaration

```swift
nonisolated func chartSymbolSizeScale<Domain>(domain: Domain, mapping: @escaping (Domain.Element) -> CGFloat) -> some View where Domain : Collection, Domain.Element : Plottable

```

## Parameters

- **domain**: The possible data values plotted as symbol size in the chart.
- **mapping**: Maps data categories to symbol sizes.

## Symbol size scales

- **chartSymbolSizeScale(_:)**: Configures the symbol size scale for charts.
- **chartSymbolSizeScale(domain:range:type:)**: Configures the symbol size scale for charts.
- **chartSymbolSizeScale(domain:type:)**: Configures the symbol size scale for charts.
- **chartSymbolSizeScale(mapping:)**: Configures the symbol size scale for charts.
- **chartSymbolSizeScale(range:type:)**: Configures the symbol size scale for charts.
- **chartSymbolSizeScale(type:)**: Configures the symbol size scale for charts.

