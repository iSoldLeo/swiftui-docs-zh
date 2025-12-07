--- 来源：https://developer.apple.com/documentation/SwiftUI/View/chartXVisibleDomain(length:)

抓取时间：2025-12-03T05:35:04Z

---

# chartXVisibleDomain(length:)

**实例方法**

设置 X 轴方向的可见区域长度。

## 声明

```swift
nonisolated func chartXVisibleDomain<P>(length: P) -> some View where P : Plottable, P : Numeric

```

## 参数

- **length**：以数据单位衡量的可见区域长度。对于分类数据，此值应为可见类别的数量。

## 说明

使用此方法可以控制可滚动图表中图表的可见范围。以下示例将图表在 X 轴方向的可见部分设置为 10 个单位。

```swift
Chart(data) {
    BarMark(
        x: .value("x", $0.x),
        y: .value("y", $0.y)
    )
}
.chartScrollableAxes(.horizontal)
.chartXVisibleDomain(length: 10)
```

## 可见区域

- **chartYVisibleDomain(length:)**：设置可见区域在 Y 轴方向上的长度。


---
source: https://developer.apple.com/documentation/SwiftUI/View/chartXVisibleDomain(length:)
crawled: 2025-12-03T05:35:04Z
---

# chartXVisibleDomain(length:)

**Instance Method**

Sets the length of the visible domain in the X dimension.

## Declaration

```swift
nonisolated func chartXVisibleDomain<P>(length: P) -> some View where P : Plottable, P : Numeric

```

## Parameters

- **length**: The length of the visible domain measured in data units. For categorical data, this should be the number of visible categories.

## Discussion

Use this method to control how much of the chart is visible in a scrollable chart. The example below sets the visible portion of the chart to 10 units in the X axis.

```swift
Chart(data) {
    BarMark(
        x: .value("x", $0.x),
        y: .value("y", $0.y)
    )
}
.chartScrollableAxes(.horizontal)
.chartXVisibleDomain(length: 10)
```

## Visible domain

- **chartYVisibleDomain(length:)**: Sets the length of the visible domain in the Y dimension.

