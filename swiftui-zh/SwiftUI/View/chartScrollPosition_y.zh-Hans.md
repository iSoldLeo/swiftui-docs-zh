--- 来源：https://developer.apple.com/documentation/SwiftUI/View/chartScrollPosition(y:)

抓取时间：2025-12-01T10:23:38Z

---

# chartScrollPosition(y:)

**实例方法**

关联一个绑定，以便在图表沿 y 轴滚动时更新。

## 声明

```swift
nonisolated func chartScrollPosition(y: Binding<some Plottable>) -> some View

```

## 滚动

- **chartScrollPosition(initialX:)**：设置沿 x 轴的初始滚动位置。一旦用户滚动滚动视图，此修饰符的值将不再生效。

- **chartScrollPosition(initialY:)**：设置沿 y 轴的初始滚动位置。一旦用户滚动滚动视图，此修饰符的值将不再生效。

- **chartScrollPosition(x:)**：关联一个绑定，以便在图表沿 x 轴滚动时更新。

- **chartScrollTargetBehavior(_:)**：设置可滚动图表的滚动行为。

- **chartScrollableAxes(_:)**：配置此视图中图表的滚动行为。


---
source: https://developer.apple.com/documentation/SwiftUI/View/chartScrollPosition(y:)
crawled: 2025-12-01T10:23:38Z
---

# chartScrollPosition(y:)

**Instance Method**

Associates a binding to be updated when the chart scrolls along the y-axis.

## Declaration

```swift
nonisolated func chartScrollPosition(y: Binding<some Plottable>) -> some View

```

## Scrolling

- **chartScrollPosition(initialX:)**: Sets the initial scroll position along the x-axis. Once the user scrolls the scroll view, the value provided to this modifier will have no effect.
- **chartScrollPosition(initialY:)**: Sets the initial scroll position along the y-axis. Once the user scrolls the scroll view, the value provided to this modifier will have no effect.
- **chartScrollPosition(x:)**: Associates a binding to be updated when the chart scrolls along the x-axis.
- **chartScrollTargetBehavior(_:)**: Sets the scroll behavior of the scrollable chart.
- **chartScrollableAxes(_:)**: Configures the scrollable behavior of charts in this view.

