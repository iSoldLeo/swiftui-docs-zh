--- 来源：https://developer.apple.com/documentation/SwiftUI/View/progressViewStyle(_:)

抓取时间：2025-11-30T21:18:24Z

---

# progressViewStyle(_:)

**实例方法**

设置此视图中进度条的样式。

## 声明

```swift
nonisolated func progressViewStyle<S>(_ style: S) -> some View where S : ProgressViewStyle

```

## 参数

- **style**：此视图要使用的进度条样式。

## 说明

例如，以下代码创建了一个使用“圆形”样式的进度条：

```swift
ProgressView()
    .progressViewStyle(.circular)
```

## 指示值

- **Gauge**：显示指定范围内值的视图。

- **gaugeStyle(_:)**：设置此视图中仪表盘的样式。

- **ProgressView**：显示任务完成进度的视图。

- **DefaultDateProgressLabel**：日期相关进度视图中当前值标签的默认类型。

- **DefaultButtonLabel**：按钮的默认标签。


---
source: https://developer.apple.com/documentation/SwiftUI/View/progressViewStyle(_:)
crawled: 2025-11-30T21:18:24Z
---

# progressViewStyle(_:)

**Instance Method**

Sets the style for progress views in this view.

## Declaration

```swift
nonisolated func progressViewStyle<S>(_ style: S) -> some View where S : ProgressViewStyle

```

## Parameters

- **style**: The progress view style to use for this view.

## Discussion

For example, the following code creates a progress view that uses the “circular” style:

```swift
ProgressView()
    .progressViewStyle(.circular)
```

## Indicating a value

- **Gauge**: A view that shows a value within a range.
- **gaugeStyle(_:)**: Sets the style for gauges within this view.
- **ProgressView**: A view that shows the progress toward completion of a task.
- **DefaultDateProgressLabel**: The default type of the current value label when used by a date-relative progress view.
- **DefaultButtonLabel**: The default label to use for a button.

