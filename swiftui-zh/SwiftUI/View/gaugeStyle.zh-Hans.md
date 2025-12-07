--- 来源：https://developer.apple.com/documentation/SwiftUI/View/gaugeStyle(_:)

抓取时间：2025-11-30T21:18:21Z

---

# gaugeStyle(_:)

**实例方法**

设置此视图中仪表盘的样式。

## 声明

```swift
nonisolated func gaugeStyle<S>(_ style: S) -> some View where S : GaugeStyle

```

## 指示值

- **Gauge**：显示某个范围内值的视图。

- **ProgressView**：显示任务完成进度的视图。

- **progressViewStyle(_:)**：设置此视图中进度视图的样式。

- **DefaultDateProgressLabel**：日期相关进度视图使用时，当前值标签的默认类型。

- **DefaultButtonLabel**：按钮的默认标签。


---
source: https://developer.apple.com/documentation/SwiftUI/View/gaugeStyle(_:)
crawled: 2025-11-30T21:18:21Z
---

# gaugeStyle(_:)

**Instance Method**

Sets the style for gauges within this view.

## Declaration

```swift
nonisolated func gaugeStyle<S>(_ style: S) -> some View where S : GaugeStyle

```

## Indicating a value

- **Gauge**: A view that shows a value within a range.
- **ProgressView**: A view that shows the progress toward completion of a task.
- **progressViewStyle(_:)**: Sets the style for progress views in this view.
- **DefaultDateProgressLabel**: The default type of the current value label when used by a date-relative progress view.
- **DefaultButtonLabel**: The default label to use for a button.

