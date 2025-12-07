---
来源： https://developer.apple.com/documentation/SwiftUI/GaugeStyleConfiguration
抓取时间： 2025-12-02T17:33:12Z
---

# GaugeStyleConfiguration

**Structure**

仪表实例的属性。

## 声明

```swift
struct GaugeStyleConfiguration
```

## 描述仪表的用途

- **label**：描述仪器用途的视图。
- **GaugeStyleConfiguration.Label**：量规的分型标签，用于描述量规的用途。

## 报告量程

- **minimumValueLabel**：描述当前值的最小量程的视图。
- **GaugeStyleConfiguration.MinimumValueLabel**：描述最小值的量规类型化值标签。
- **maximumValueLabel**：描述当前值范围最大值的视图。
- **GaugeStyleConfiguration.MaximumValueLabel**：描述最大值的量规类型化值标签。

## 设置数值

- **value**：仪表的当前值。
- **currentValueLabel**：描述当前值的视图。
- **GaugeStyleConfiguration.CurrentValueLabel**：包含当前值的量规的类型化值标签。
- **GaugeStyleConfiguration.MarkedValueLabel**：描述量规特定值的类型迭代标签。

### 造型指标

- **gaugeStyle(_:)**：为该视图中的仪表设置样式。
- **GaugeStyle**：定义视图层次结构中所有仪表实例的实现。
- **progressViewStyle(_:)**：为该视图中的进度视图设置样式。
- **ProgressViewStyle**：对视图层次结构中的所有进度视图应用标准交互行为的类型。
- **ProgressViewStyleConfiguration**：进度视图实例的属性。


---
source: https://developer.apple.com/documentation/SwiftUI/GaugeStyleConfiguration
crawled: 2025-12-02T17:33:12Z
---

# GaugeStyleConfiguration

**Structure**

The properties of a gauge instance.

## Declaration

```swift
struct GaugeStyleConfiguration
```

## Describing the purpose of the gauge

- **label**: A view that describes the purpose of the gauge.
- **GaugeStyleConfiguration.Label**: A type-erased label of a gauge, describing its purpose.

## Reporting the range

- **minimumValueLabel**: A view that describes the minimum of the range for the current value.
- **GaugeStyleConfiguration.MinimumValueLabel**: A type-erased value label of a gauge describing the minimum value.
- **maximumValueLabel**: A view that describes the maximum of the range for the current value.
- **GaugeStyleConfiguration.MaximumValueLabel**: A type-erased value label of a gauge describing the maximum value.

## Setting the value

- **value**: The current value of the gauge.
- **currentValueLabel**: A view that describes the current value.
- **GaugeStyleConfiguration.CurrentValueLabel**: A type-erased value label of a gauge that contains the current value.
- **GaugeStyleConfiguration.MarkedValueLabel**: A type-erased label describing a specific value of a gauge.

## Styling indicators

- **gaugeStyle(_:)**: Sets the style for gauges within this view.
- **GaugeStyle**: Defines the implementation of all gauge instances within a view hierarchy.
- **progressViewStyle(_:)**: Sets the style for progress views in this view.
- **ProgressViewStyle**: A type that applies standard interaction behavior to all progress views within a view hierarchy.
- **ProgressViewStyleConfiguration**: The properties of a progress view instance.

