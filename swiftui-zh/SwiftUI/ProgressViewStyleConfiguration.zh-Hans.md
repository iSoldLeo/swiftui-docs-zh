--- 来源：https://developer.apple.com/documentation/SwiftUI/ProgressViewStyleConfiguration
抓取时间：2025-12-02T17:33:14Z

---

# ProgressViewStyleConfiguration

**Structure**

进度视图实例的属性。

## 声明

```swift
struct ProgressViewStyleConfiguration
```

## 配置标签

- **label**：描述进度视图所代表任务的视图。

- **ProgressViewStyleConfiguration.Label**：描述进度视图所代表任务的已擦除类型的标签。

## 配置当前值标签

- **currentValueLabel**：描述进度视图当前值的视图。

- **ProgressViewStyleConfiguration.CurrentValueLabel**：用于描述进度视图当前值的已擦除标签。

## 配置进度完成情况

- **fractionCompleted**：进度视图所表示的任务已完成部分，从 `0.0`（尚未开始）到 `1.0`（完全完成），如果进度不确定或与日期区间相关，则为 `nil`。

## 设置指示器样式

- **gaugeStyle(_:)**：设置此视图中仪表盘的样式。

- **GaugeStyle**：定义视图层次结构中所有仪表盘实例的实现方式。

- **GaugeStyleConfiguration**：仪表盘实例的属性。

- **progressViewStyle(_:)**：设置此视图中进度视图的样式。

- **ProgressViewStyle**：一种将标准交互行为应用于视图层次结构中所有进度视图的类型。


---
source: https://developer.apple.com/documentation/SwiftUI/ProgressViewStyleConfiguration
crawled: 2025-12-02T17:33:14Z
---

# ProgressViewStyleConfiguration

**Structure**

The properties of a progress view instance.

## Declaration

```swift
struct ProgressViewStyleConfiguration
```

## Configuring the label

- **label**: A view that describes the task represented by the progress view.
- **ProgressViewStyleConfiguration.Label**: A type-erased label describing the task represented by the progress view.

## Configuring the current value label

- **currentValueLabel**: A view that describes the current value of a progress view.
- **ProgressViewStyleConfiguration.CurrentValueLabel**: A type-erased label that describes the current value of a progress view.

## Configuring progress completion

- **fractionCompleted**: The completed fraction of the task represented by the progress view, from `0.0` (not yet started) to `1.0` (fully complete), or `nil` if the progress is indeterminate or relative to a date interval.

## Styling indicators

- **gaugeStyle(_:)**: Sets the style for gauges within this view.
- **GaugeStyle**: Defines the implementation of all gauge instances within a view hierarchy.
- **GaugeStyleConfiguration**: The properties of a gauge instance.
- **progressViewStyle(_:)**: Sets the style for progress views in this view.
- **ProgressViewStyle**: A type that applies standard interaction behavior to all progress views within a view hierarchy.

