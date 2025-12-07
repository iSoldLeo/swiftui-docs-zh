--- 来源：https://developer.apple.com/documentation/SwiftUI/View/chartSymbolScale(mapping:)

抓取时间：2025-12-01T10:23:25Z

---

# chartSymbolScale(mapping:)

**实例方法**

配置图表符号的刻度。

## 声明

```swift
nonisolated func chartSymbolScale<DataValue, S>(mapping: @escaping (DataValue) -> S) -> some View where DataValue : Plottable, S : ChartSymbolShape

```

## 参数

- **mapping**：将数据类别映射到符号形状。

## 符号刻度

- **chartSymbolScale(_:)**：配置图表符号的刻度。

- **chartSymbolScale(domain:)**：配置图表符号样式的刻度。

- **chartSymbolScale(domain:range:)**：配置图表符号样式的刻度。

- **chartSymbolScale(domain:mapping:)**：配置图表符号刻度。

- **chartSymbolScale(range:)**：配置图表符号样式刻度。


---
source: https://developer.apple.com/documentation/SwiftUI/View/chartSymbolScale(mapping:)
crawled: 2025-12-01T10:23:25Z
---

# chartSymbolScale(mapping:)

**Instance Method**

Configures the symbol scale for charts.

## Declaration

```swift
nonisolated func chartSymbolScale<DataValue, S>(mapping: @escaping (DataValue) -> S) -> some View where DataValue : Plottable, S : ChartSymbolShape

```

## Parameters

- **mapping**: Maps data categories to symbol shapes.

## Symbol scales

- **chartSymbolScale(_:)**: Configures the symbol scale for charts.
- **chartSymbolScale(domain:)**: Configures the symbol style scale for charts.
- **chartSymbolScale(domain:range:)**: Configures the symbol style scale for charts.
- **chartSymbolScale(domain:mapping:)**: Configures the symbol scale for charts.
- **chartSymbolScale(range:)**: Configures the symbol style scale for charts.

