--- 来源：https://developer.apple.com/documentation/SwiftUI/AccessoryLinearGaugeStyle
抓取时间：2025-12-03T06:10:14Z

---

# AccessoryLinearGaugeStyle

**Structure**

一种仪表样式，它会显示一个带有标记的条形，该标记位于条形上的某个点，用于指示仪表的当前值。

## 声明

```swift
@MainActor @preconcurrency struct AccessoryLinearGaugeStyle
```

## 概述

使用 [accessoryLinear](GaugeStyle/accessoryLinear.zh-Hans.md) 来构造此样式。

## 创建仪表样式

- **init()**：创建一个辅助线性仪表样式。

## 支持的类型

- **DefaultGaugeStyle**：当前视图上下文中的默认仪表视图样式。

- **CircularGaugeStyle**：一种仪表样式，显示一个开口圆环，圆环上会显示一个标记，指示仪表的当前值。

- **AccessoryCircularGaugeStyle**：一种仪表样式，显示一个开口圆环，圆环上会显示一个标记，指示仪表的当前值。

- **AccessoryCircularCapacityGaugeStyle**：一种仪表样式，显示一个部分填充的闭合圆环，指示仪表的当前值。

- **LinearGaugeStyle**：一种仪表样式，显示一个条形，条形上会显示一个标记，指示仪表的当前值。

- **LinearCapacityGaugeStyle**：一种仪表样式，显示一个条形，随着仪表当前值的增加，条形会从前缘向后缘逐渐填充。

- **AccessoryLinearCapacityGaugeStyle**：一种仪表样式，其条形图会随着仪表当前值的增加而从前沿填充到后沿。

## 符合以下规范

- GaugeStyle


---
source: https://developer.apple.com/documentation/SwiftUI/AccessoryLinearGaugeStyle
crawled: 2025-12-03T06:10:14Z
---

# AccessoryLinearGaugeStyle

**Structure**

A gauge style that displays bar with a marker that appears at a point along the bar to indicate the gauge’s current value.

## Declaration

```swift
@MainActor @preconcurrency struct AccessoryLinearGaugeStyle
```

## Overview

Use [accessoryLinear](GaugeStyle/accessoryLinear.zh-Hans.md) to construct this style.

## Creating the gauge style

- **init()**: Creates an accessory linear gauge style.

## Supporting types

- **DefaultGaugeStyle**: The default gauge view style in the current context of the view being styled.
- **CircularGaugeStyle**: A gauge style that displays an open ring with a marker that appears at a point along the ring to indicate the gauge’s current value.
- **AccessoryCircularGaugeStyle**: A gauge style that displays an open ring with a marker that appears at a point along the ring to indicate the gauge’s current value.
- **AccessoryCircularCapacityGaugeStyle**: A gauge style that displays a closed ring that’s partially filled in to indicate the gauge’s current value.
- **LinearGaugeStyle**: A gauge style that displays a bar with a marker that appears at a point along the bar to indicate the gauge’s current value.
- **LinearCapacityGaugeStyle**: A gauge style that displays bar that fills from leading to trailing edges as the gauge’s current value increases.
- **AccessoryLinearCapacityGaugeStyle**: A gauge style that displays bar that fills from leading to trailing edges as the gauge’s current value increases.

## Conforms To

- GaugeStyle

