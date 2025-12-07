--- 来源：https://developer.apple.com/documentation/SwiftUI/View/chartZScale(domain:type:)

抓取时间：2025-11-30T21:07:58Z

---

# chartZScale(domain:type:)

**实例方法**

配置 3D 图表的 Z 轴刻度。

## 声明

```swift
nonisolated func chartZScale<Domain>(domain: Domain, type: ScaleType? = nil) -> some View where Domain : ScaleDomain

```

## 参数

- **domain**：图表中 Z 轴的可能数据值。您可以使用 `ClosedRange` 定义数值域（例如，`0 ... 500`）。

- **type**：刻度类型。


---
source: https://developer.apple.com/documentation/SwiftUI/View/chartZScale(domain:type:)
crawled: 2025-11-30T21:07:58Z
---

# chartZScale(domain:type:)

**Instance Method**

Configures the z scale for 3D charts.

## Declaration

```swift
nonisolated func chartZScale<Domain>(domain: Domain, type: ScaleType? = nil) -> some View where Domain : ScaleDomain

```

## Parameters

- **domain**: The possible data values along the z axis in the chart. You can define the domain with a `ClosedRange` for numeric values (e.g., `0 ... 500`).
- **type**: The scale type.

