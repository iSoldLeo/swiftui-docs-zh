--- 来源：https://developer.apple.com/documentation/SwiftUI/View/chartSymbolSizeScale(domain:range:type:)

抓取时间：2025-12-03T05:34:20Z

---

# chartSymbolSizeScale(domain:range:type:)

**实例方法**

配置图表符号大小刻度。

## 声明

```swift
nonisolated func chartSymbolSizeScale<Domain, Range>(domain: Domain, range: Range, type: ScaleType? = nil) -> some View where Domain : ScaleDomain, Range : ScaleRange, Range.VisualValue == CGFloat

```

## 参数

- **domain**：图表中可绘制为符号大小的数据值。您可以为分类值定义一个数组作为域（例如，`["A", "B", "C"]`）。

- **range**：与刻度域对应的符号大小范围。

- **type**：刻度类型。

## 符号大小比例

- **chartSymbolSizeScale(_:)**：配置图表符号大小比例。

- **chartSymbolSizeScale(domain:type:)**：配置图表符号大小比例。

- **chartSymbolSizeScale(domain:mapping:)**：配置图表符号大小比例。

- **chartSymbolSizeScale(mapping:)**：配置图表符号大小比例。

- **chartSymbolSizeScale(range:type:)**：配置图表符号大小比例。

- **chartSymbolSizeScale(type:)**：配置图表符号大小比例。


---
source: https://developer.apple.com/documentation/SwiftUI/View/chartSymbolSizeScale(domain:range:type:)
crawled: 2025-12-03T05:34:20Z
---

# chartSymbolSizeScale(domain:range:type:)

**Instance Method**

Configures the symbol size scale for charts.

## Declaration

```swift
nonisolated func chartSymbolSizeScale<Domain, Range>(domain: Domain, range: Range, type: ScaleType? = nil) -> some View where Domain : ScaleDomain, Range : ScaleRange, Range.VisualValue == CGFloat

```

## Parameters

- **domain**: The possible data values plotted as symbol sizes in the chart. You can define the domain with an array for categorical values (e.g., `["A", "B", "C"]`)
- **range**: The range of symbol size that correspond to the scale domain.
- **type**: The scale type.

## Symbol size scales

- **chartSymbolSizeScale(_:)**: Configures the symbol size scale for charts.
- **chartSymbolSizeScale(domain:type:)**: Configures the symbol size scale for charts.
- **chartSymbolSizeScale(domain:mapping:)**: Configures the symbol size scale for charts.
- **chartSymbolSizeScale(mapping:)**: Configures the symbol size scale for charts.
- **chartSymbolSizeScale(range:type:)**: Configures the symbol size scale for charts.
- **chartSymbolSizeScale(type:)**: Configures the symbol size scale for charts.

