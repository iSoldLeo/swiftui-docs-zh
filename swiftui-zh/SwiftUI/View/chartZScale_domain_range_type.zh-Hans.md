--- 来源：https://developer.apple.com/documentation/SwiftUI/View/chartZScale(domain:range:type:)

抓取时间：2025-11-30T21:07:57Z

---

# chartZScale(domain:range:type:)

**实例方法**

配置 3D 图表的 Z 轴刻度。

## 声明

```swift
nonisolated func chartZScale<Domain, Range>(domain: Domain, range: Range, type: ScaleType? = nil) -> some View where Domain : ScaleDomain, Range : PositionScaleRange

```

## 参数

- **domain**：图表中 Z 轴的可能数据值。您可以使用 `ClosedRange` 定义数值域。

- **range**：与刻度域对应的 x 轴位置范围。默认情况下，该范围由绘图区域的尺寸决定。

- **type**：刻度类型。


---
source: https://developer.apple.com/documentation/SwiftUI/View/chartZScale(domain:range:type:)
crawled: 2025-11-30T21:07:57Z
---

# chartZScale(domain:range:type:)

**Instance Method**

Configures the z scale for 3D charts.

## Declaration

```swift
nonisolated func chartZScale<Domain, Range>(domain: Domain, range: Range, type: ScaleType? = nil) -> some View where Domain : ScaleDomain, Range : PositionScaleRange

```

## Parameters

- **domain**: The possible data values along the z axis in the chart. You can define the domain with a `ClosedRange` for numeric values.
- **range**: The range of x positions that correspond to the scale domain. By default the range is determined by the dimension of the plot area.
- **type**: The scale type.

