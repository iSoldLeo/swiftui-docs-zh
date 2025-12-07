--- 来源：https://developer.apple.com/documentation/SwiftUI/View/chartSymbolScale(_:)

抓取时间：2025-12-03T05:34:16Z

---

# chartSymbolScale(_:)

**实例方法**

配置图表符号的刻度。

## 声明

```swift
nonisolated func chartSymbolScale<DataValue, S>(_ mapping: KeyValuePairs<DataValue, S>) -> some View where DataValue : Plottable, S : ChartSymbolShape

```

## 参数

- **mapping**：将数据类别映射到符号形状。

## 符号刻度

- **chartSymbolScale(domain:)**：配置图表符号样式的刻度。

- **chartSymbolScale(domain:range:)**：配置图表符号样式的刻度。

- **chartSymbolScale(domain:mapping:)**：配置图表符号的刻度。

- **chartSymbolScale(mapping:)**：配置图表符号刻度。

- **chartSymbolScale(range:)**：配置图表符号样式刻度。


---
source: https://developer.apple.com/documentation/SwiftUI/View/chartSymbolScale(_:)
crawled: 2025-12-03T05:34:16Z
---

# chartSymbolScale(_:)

**Instance Method**

Configures the symbol scale for charts.

## Declaration

```swift
nonisolated func chartSymbolScale<DataValue, S>(_ mapping: KeyValuePairs<DataValue, S>) -> some View where DataValue : Plottable, S : ChartSymbolShape

```

## Parameters

- **mapping**: Maps data categories to symbol shapes.

## Symbol scales

- **chartSymbolScale(domain:)**: Configures the symbol style scale for charts.
- **chartSymbolScale(domain:range:)**: Configures the symbol style scale for charts.
- **chartSymbolScale(domain:mapping:)**: Configures the symbol scale for charts.
- **chartSymbolScale(mapping:)**: Configures the symbol scale for charts.
- **chartSymbolScale(range:)**: Configures the symbol style scale for charts.

