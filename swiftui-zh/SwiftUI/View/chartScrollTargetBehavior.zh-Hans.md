--- 来源：https://developer.apple.com/documentation/SwiftUI/View/chartScrollTargetBehavior(_:)

抓取时间：2025-12-01T10:23:39Z

---

# chartScrollTargetBehavior(_:)

**实例方法**

设置可滚动图表的滚动行为。

## 声明

```swift
nonisolated func chartScrollTargetBehavior(_ behavior: some ChartScrollTargetBehavior) -> some View

```

## 参数

- **behavior**：图表滚动目标行为。

## 说明

使用此方法控制图表的滚动方式以及用户停止滚动后图表的对齐方式。以下示例将滚动目标行为设置为与图表中的值对齐。当用户停止滚动时，图表将自动调整为与图表中的值对齐。

```swift
Chart(data) {
    BarMark(
        x: .value("x", $0.x),
        y: .value("y", $0.y)
    )
}
.chartScrollableAxes(.vertical)
.chartYVisibleDomain(length: 10)
.chartScrollTargetBehavior(.valueAligned(unit: 1))
```

## 滚动

- **chartScrollPosition(initialX:)**：设置沿 x 轴的初始滚动位置。一旦用户滚动了滚动视图，此参数的值将失效。

- **chartScrollPosition(initialY:)**：设置沿 y 轴的初始滚动位置。一旦用户滚动了滚动视图，此参数的值将失效。

- **chartScrollPosition(x:)**：关联一个绑定，以便在图表沿 x 轴滚动时更新。

- **chartScrollPosition(y:)**：关联一个绑定，以便在图表沿 y 轴滚动时更新。

- **chartScrollableAxes(_:)**：配置此视图中图表的滚动行为。


---
source: https://developer.apple.com/documentation/SwiftUI/View/chartScrollTargetBehavior(_:)
crawled: 2025-12-01T10:23:39Z
---

# chartScrollTargetBehavior(_:)

**Instance Method**

Sets the scroll behavior of the scrollable chart.

## Declaration

```swift
nonisolated func chartScrollTargetBehavior(_ behavior: some ChartScrollTargetBehavior) -> some View

```

## Parameters

- **behavior**: The chart scroll target behavior.

## Discussion

Use this method to control how the chart scrolls and aligns when the user finishes scrolling. The example below sets the scroll target behavior to align to the values in the chart. When the user finishes scrolling, the chart will settle to align with the values in the chart.

```swift
Chart(data) {
    BarMark(
        x: .value("x", $0.x),
        y: .value("y", $0.y)
    )
}
.chartScrollableAxes(.vertical)
.chartYVisibleDomain(length: 10)
.chartScrollTargetBehavior(.valueAligned(unit: 1))
```

## Scrolling

- **chartScrollPosition(initialX:)**: Sets the initial scroll position along the x-axis. Once the user scrolls the scroll view, the value provided to this modifier will have no effect.
- **chartScrollPosition(initialY:)**: Sets the initial scroll position along the y-axis. Once the user scrolls the scroll view, the value provided to this modifier will have no effect.
- **chartScrollPosition(x:)**: Associates a binding to be updated when the chart scrolls along the x-axis.
- **chartScrollPosition(y:)**: Associates a binding to be updated when the chart scrolls along the y-axis.
- **chartScrollableAxes(_:)**: Configures the scrollable behavior of charts in this view.

