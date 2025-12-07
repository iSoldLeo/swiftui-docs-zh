---
来源： https://developer.apple.com/documentation/SwiftUI/DefaultGaugeStyle
抓取时间： 2025-12-03T06:10:10Z
---

# 默认仪表盘样式

**Structure**

当前样式化视图上下文中的默认仪表盘视图样式。

## 声明

```swift
@MainActor @preconcurrency struct DefaultGaugeStyle
```

## 概览

您也可以使用 [automatic](GaugeStyle/automatic.zh-Hans.md) 构建这种样式。

## 创建仪表样式

- **init()**：创建默认的仪表盘样式。

## 支持类型

- **CircularGaugeStyle**：仪表样式，显示一个开放的环，环上的某一点会出现一个标记，指示仪表的当前值。
- **AccessoryCircularGaugeStyle**：一种仪器样式，显示一个开放的环，环上的某一点会出现一个标记，指示仪器的当前值。
- **AccessoryCircularCapacityGaugeStyle**：一种仪表样式，显示一个部分填满的封闭环，以指示仪表的当前值。
- **LinearGaugeStyle**：一种仪表样式，显示带有标记的条形图，标记出现在条形图上的某一点，以指示仪表的当前值。
- **LinearCapacityGaugeStyle**：一种仪表样式，随着仪表当前值的增加，显示从前缘到后缘填充的条形图。
- **AccessoryLinearGaugeStyle**：一种仪表样式，用于显示带有标记的条形图，标记会出现在条形图上的某一点，以指示仪表的当前值。
- **AccessoryLinearCapacityGaugeStyle**：一种仪表盘样式，显示条形图，随着仪表盘当前值的增加，条形图从前缘向后缘填充。

## 符合

- GaugeStyle


---
source: https://developer.apple.com/documentation/SwiftUI/DefaultGaugeStyle
crawled: 2025-12-03T06:10:10Z
---

# DefaultGaugeStyle

**Structure**

The default gauge view style in the current context of the view being styled.

## Declaration

```swift
@MainActor @preconcurrency struct DefaultGaugeStyle
```

## Overview

You can also use [automatic](GaugeStyle/automatic.zh-Hans.md) to construct this style.

## Creating the gauge style

- **init()**: Creates a default gauge style.

## Supporting types

- **CircularGaugeStyle**: A gauge style that displays an open ring with a marker that appears at a point along the ring to indicate the gauge’s current value.
- **AccessoryCircularGaugeStyle**: A gauge style that displays an open ring with a marker that appears at a point along the ring to indicate the gauge’s current value.
- **AccessoryCircularCapacityGaugeStyle**: A gauge style that displays a closed ring that’s partially filled in to indicate the gauge’s current value.
- **LinearGaugeStyle**: A gauge style that displays a bar with a marker that appears at a point along the bar to indicate the gauge’s current value.
- **LinearCapacityGaugeStyle**: A gauge style that displays bar that fills from leading to trailing edges as the gauge’s current value increases.
- **AccessoryLinearGaugeStyle**: A gauge style that displays bar with a marker that appears at a point along the bar to indicate the gauge’s current value.
- **AccessoryLinearCapacityGaugeStyle**: A gauge style that displays bar that fills from leading to trailing edges as the gauge’s current value increases.

## Conforms To

- GaugeStyle

