--- 来源：https://developer.apple.com/documentation/SwiftUI/AccessoryLinearCapacityGaugeStyle
抓取时间：2025-12-03T06:10:15Z

---

# AccessoryLinearCapacityGaugeStyle

**Structure**

一种仪表样式，其条形图会随着仪表当前值的增加而从前缘填充到后缘。

## 声明

```swift
@MainActor @preconcurrency struct AccessoryLinearCapacityGaugeStyle
```

## 概述

使用 [accessoryLinearCapacity](GaugeStyle/accessoryLinearCapacity.zh-Hans.md) 来构造此样式。

## 创建仪表样式

- **init()**：创建一个辅助线性容量仪表样式。

## 支持的类型

- **DefaultGaugeStyle**：当前视图上下文中的默认仪表视图样式。

- **CircularGaugeStyle**：一种仪表样式，显示一个开口圆环，圆环上会显示一个标记，指示仪表的当前值。

- **AccessoryCircularGaugeStyle**：一种仪表样式，显示一个开口圆环，圆环上会显示一个标记，指示仪表的当前值。

- **AccessoryCircularCapacityGaugeStyle**：一种仪表样式，显示一个部分填充的闭合圆环，指示仪表的当前值。

- **LinearGaugeStyle**：一种仪表样式，显示一个条形，条形上会显示一个标记，指示仪表的当前值。

- **LinearCapacityGaugeStyle**：一种仪表样式，显示一个条形，随着仪表当前值的增加，条形会从前缘向后缘逐渐填充。

- **AccessoryLinearGaugeStyle**：一种仪表样式，其条形图上会显示一个标记，该标记位于条形图上的某个位置，用于指示仪表的当前值。

## 符合以下规范

- GaugeStyle


---
source: https://developer.apple.com/documentation/SwiftUI/AccessoryLinearCapacityGaugeStyle
crawled: 2025-12-03T06:10:15Z
---

# AccessoryLinearCapacityGaugeStyle

**Structure**

A gauge style that displays bar that fills from leading to trailing edges as the gauge’s current value increases.

## Declaration

```swift
@MainActor @preconcurrency struct AccessoryLinearCapacityGaugeStyle
```

## Overview

Use [accessoryLinearCapacity](GaugeStyle/accessoryLinearCapacity.zh-Hans.md) to construct this style.

## Creating the gauge style

- **init()**: Creates an accessory linear capacity gauge style.

## Supporting types

- **DefaultGaugeStyle**: The default gauge view style in the current context of the view being styled.
- **CircularGaugeStyle**: A gauge style that displays an open ring with a marker that appears at a point along the ring to indicate the gauge’s current value.
- **AccessoryCircularGaugeStyle**: A gauge style that displays an open ring with a marker that appears at a point along the ring to indicate the gauge’s current value.
- **AccessoryCircularCapacityGaugeStyle**: A gauge style that displays a closed ring that’s partially filled in to indicate the gauge’s current value.
- **LinearGaugeStyle**: A gauge style that displays a bar with a marker that appears at a point along the bar to indicate the gauge’s current value.
- **LinearCapacityGaugeStyle**: A gauge style that displays bar that fills from leading to trailing edges as the gauge’s current value increases.
- **AccessoryLinearGaugeStyle**: A gauge style that displays bar with a marker that appears at a point along the bar to indicate the gauge’s current value.

## Conforms To

- GaugeStyle

