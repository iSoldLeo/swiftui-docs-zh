--- 来源：https://developer.apple.com/documentation/SwiftUI/View/chartYScale(domain:range:type:)

抓取时间：2025-12-03T05:34:13Z

---

# chartYScale(domain:range:type:)

**实例方法**

配置图表的 y 轴刻度。

## 声明

```swift
nonisolated func chartYScale<Domain, Range>(domain: Domain, range: Range, type: ScaleType? = nil) -> some View where Domain : ScaleDomain, Range : PositionScaleRange

```

## 参数

- **domain**：图表中 y 轴的可能数据值。您可以使用 `ClosedRange` 定义数值域，或使用 `Date` 定义分类值域（例如 `0 ... 500`），或使用数组定义分类值域（例如 `["A", "B", "C"]`）。

- **range**：对应于刻度域的 y 轴位置范围。默认情况下，该范围由绘图区域的尺寸决定。您可以使用 `range: .plotDimension(startPadding:, endPadding:)` 为刻度范围添加填充。

- **type**：刻度类型。

## 坐标轴刻度

- **chartXScale(domain:range:type:)**：配置图表的 x 轴刻度。

- **chartXScale(domain:type:)**：配置图表的 x 轴刻度。

- **chartXScale(range:type:)**：配置图表的 x 轴刻度。

- **chartXScale(type:)**：配置图表的 x 轴刻度。

- **chartYScale(domain:type:)**：配置图表的 y 轴刻度。

- **chartYScale(range:type:)**：配置图表的 y 轴刻度。

- **chartYScale(type:)**：配置图表的 y 轴刻度。


---
source: https://developer.apple.com/documentation/SwiftUI/View/chartYScale(domain:range:type:)
crawled: 2025-12-03T05:34:13Z
---

# chartYScale(domain:range:type:)

**Instance Method**

Configures the y scale for charts.

## Declaration

```swift
nonisolated func chartYScale<Domain, Range>(domain: Domain, range: Range, type: ScaleType? = nil) -> some View where Domain : ScaleDomain, Range : PositionScaleRange

```

## Parameters

- **domain**: The possible data values along the y axis in the chart. You can define the domain with a `ClosedRange` for number or `Date` values (e.g., `0 ... 500`), and with an array for categorical values (e.g., `["A", "B", "C"]`)
- **range**: The range of y positions that correspond to the scale domain. By default the range is determined by the dimension of the plot area. You can use `range: .plotDimension(startPadding:, endPadding:)` to add padding to the scale range.
- **type**: The scale type.

## Axis scales

- **chartXScale(domain:range:type:)**: Configures the x scale for charts.
- **chartXScale(domain:type:)**: Configures the x scale for charts.
- **chartXScale(range:type:)**: Configures the x scale for charts.
- **chartXScale(type:)**: Configures the x scale for charts.
- **chartYScale(domain:type:)**: Configures the y scale for charts.
- **chartYScale(range:type:)**: Configures the y scale for charts.
- **chartYScale(type:)**: Configures the y scale for charts.

