--- 来源：https://developer.apple.com/documentation/SwiftUI/View/chartZScale(range:type:)

抓取时间：2025-11-30T21:07:59Z

---

# chartZScale(range:type:)

**实例方法**

配置 3D 图表的 Z 轴刻度。

## 声明

```swift
nonisolated func chartZScale<Range>(range: Range, type: ScaleType? = nil) -> some View where Range : PositionScaleRange

```

## 参数

- **range**：对应于刻度域的 Z 轴位置范围。默认情况下，该范围由绘图区域的尺寸决定。

- **type**：刻度类型。


---
source: https://developer.apple.com/documentation/SwiftUI/View/chartZScale(range:type:)
crawled: 2025-11-30T21:07:59Z
---

# chartZScale(range:type:)

**Instance Method**

Configures the z scale for 3D charts.

## Declaration

```swift
nonisolated func chartZScale<Range>(range: Range, type: ScaleType? = nil) -> some View where Range : PositionScaleRange

```

## Parameters

- **range**: The range of z positions that correspond to the scale domain. By default the range is determined by the dimension of the plot area.
- **type**: The scale type.

