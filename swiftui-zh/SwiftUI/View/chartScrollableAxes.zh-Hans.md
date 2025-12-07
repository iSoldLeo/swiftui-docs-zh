--- 来源：https://developer.apple.com/documentation/SwiftUI/View/chartScrollableAxes(_:)

抓取时间：2025-12-01T10:23:40Z

---

# chartScrollableAxes(_:)

**实例方法**

配置此视图中图表的滚动行为。

## 声明

```swift
nonisolated func chartScrollableAxes(_ axes: Axis.Set) -> some View

```

## 参数

- **axes**：要启用滚动的坐标轴集合。

## 说明

使用此方法可使图表可滚动。以下示例演示如何使图表沿水平轴滚动。

```swift
Chart(data) {
    BarMark(
        x: .value("x", $0.x),
        y: .value("y", $0.y)
    )
}
.chartScrollableAxes(.horizontal)
```

## 滚动

- **chartScrollPosition(initialX:)**：设置沿 x 轴的初始滚动位置。用户滚动滚动视图后，此修饰符的值将失效。

- **chartScrollPosition(initialY:)**：设置沿 y 轴的初始滚动位置。用户滚动滚动视图后，此修饰符的值将失效。

- **chartScrollPosition(x:)**：关联一个绑定，以便在图表沿 x 轴滚动时更新。

- **chartScrollPosition(y:)**：关联一个绑定，以便在图表沿 y 轴滚动时更新。

- **chartScrollTargetBehavior(_:)**：设置可滚动图表的滚动行为。


---
source: https://developer.apple.com/documentation/SwiftUI/View/chartScrollableAxes(_:)
crawled: 2025-12-01T10:23:40Z
---

# chartScrollableAxes(_:)

**Instance Method**

Configures the scrollable behavior of charts in this view.

## Declaration

```swift
nonisolated func chartScrollableAxes(_ axes: Axis.Set) -> some View

```

## Parameters

- **axes**: The set of axes to enable scrolling.

## Discussion

Use this method to make a chart scrollable. Below is an example that makes a chart scrollable along the horizontal axis.

```swift
Chart(data) {
    BarMark(
        x: .value("x", $0.x),
        y: .value("y", $0.y)
    )
}
.chartScrollableAxes(.horizontal)
```



## Scrolling

- **chartScrollPosition(initialX:)**: Sets the initial scroll position along the x-axis. Once the user scrolls the scroll view, the value provided to this modifier will have no effect.
- **chartScrollPosition(initialY:)**: Sets the initial scroll position along the y-axis. Once the user scrolls the scroll view, the value provided to this modifier will have no effect.
- **chartScrollPosition(x:)**: Associates a binding to be updated when the chart scrolls along the x-axis.
- **chartScrollPosition(y:)**: Associates a binding to be updated when the chart scrolls along the y-axis.
- **chartScrollTargetBehavior(_:)**: Sets the scroll behavior of the scrollable chart.

