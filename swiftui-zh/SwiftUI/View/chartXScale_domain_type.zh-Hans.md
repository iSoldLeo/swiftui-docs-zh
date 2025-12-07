--- 来源：https://developer.apple.com/documentation/SwiftUI/View/chartXScale(domain:type:)

抓取时间：2025-12-01T10:23:16Z

---

# chartXScale(domain:type:)

**实例方法**

配置图表的 x 轴刻度。

## 声明

```swift
nonisolated func chartXScale<Domain>(domain: Domain, type: ScaleType? = nil) -> some View where Domain : ScaleDomain

```

## 参数

- **domain**：图表 x 轴上可能的数据值。您可以使用 `ClosedRange` 定义数值域，或使用 `Date` 定义分类域（例如 `0 ... 500`），或使用数组定义分类域（例如 `["A", "B", "C"]`）。

- **type**：刻度类型。

## 坐标轴刻度

- **chartXScale(domain:range:type:)**：配置图表的 x 轴刻度。

- **chartXScale(range:type:)**：配置图表的 x 轴刻度。

- **chartXScale(type:)**：配置图表的 x 轴刻度。

- **chartYScale(domain:range:type:)**：配置图表的 y 轴刻度。

- **chartYScale(domain:type:)**：配置图表的 y 轴刻度。

- **chartYScale(range:type:)**：配置图表的 y 轴刻度。

- **chartYScale(type:)**：配置图表的 y 轴刻度。


---
source: https://developer.apple.com/documentation/SwiftUI/View/chartXScale(domain:type:)
crawled: 2025-12-01T10:23:16Z
---

# chartXScale(domain:type:)

**Instance Method**

Configures the x scale for charts.

## Declaration

```swift
nonisolated func chartXScale<Domain>(domain: Domain, type: ScaleType? = nil) -> some View where Domain : ScaleDomain

```

## Parameters

- **domain**: The possible data values along the x axis in the chart. You can define the domain with a `ClosedRange` for number or `Date` values (e.g., `0 ... 500`), and with an array for categorical values (e.g., `["A", "B", "C"]`)
- **type**: The scale type.

## Axis scales

- **chartXScale(domain:range:type:)**: Configures the x scale for charts.
- **chartXScale(range:type:)**: Configures the x scale for charts.
- **chartXScale(type:)**: Configures the x scale for charts.
- **chartYScale(domain:range:type:)**: Configures the y scale for charts.
- **chartYScale(domain:type:)**: Configures the y scale for charts.
- **chartYScale(range:type:)**: Configures the y scale for charts.
- **chartYScale(type:)**: Configures the y scale for charts.

