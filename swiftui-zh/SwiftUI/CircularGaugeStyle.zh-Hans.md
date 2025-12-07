--- 来源：https://developer.apple.com/documentation/SwiftUI/CircularGaugeStyle
抓取时间：2025-12-03T06:10:10Z

---

# CircularGaugeStyle

**Structure**

一种仪表样式，显示一个带有标记的开放圆环，该标记位于圆环上的某个点，用于指示仪表的当前值。

## 声明

```swift
struct CircularGaugeStyle
```

## 概述

使用 [circular](GaugeStyle/circular.zh-Hans.md) 构建此样式。

## 创建仪表样式

- **init()**：创建一个圆形仪表。

- **init(tint:)**：创建一个以指定颜色绘制的圆形仪表。

## 支持的类型

- **DefaultGaugeStyle**：当前视图上下文中的默认仪表盘样式。

- **AccessoryCircularGaugeStyle**：一种仪表盘样式，显示一个带有标记的开放圆环，该标记位于圆环上的某个点，用于指示仪表盘的当前值。

- **AccessoryCircularCapacityGaugeStyle**：一种仪表盘样式，显示一个部分填充的闭合圆环，用于指示仪表盘的当前值。

- **LinearGaugeStyle**：一种仪表盘样式，显示一个带有标记的条形，该标记位于条形上的某个点，用于指示仪表盘的当前值。

- **LinearCapacityGaugeStyle**：一种仪表盘样式，显示一个条形，该条形会随着仪表盘当前值的增加而从前缘向后缘填充。

- **AccessoryLinearGaugeStyle**：一种仪表样式，其条形图上会显示一个标记，该标记位于条形图上的某个点，用于指示仪表的当前值。

- **AccessoryLinearCapacityGaugeStyle**：一种仪表样式，其条形图会随着仪表当前值的增加而从前缘填充到后缘。

## 符合以下规范

- GaugeStyle


---
source: https://developer.apple.com/documentation/SwiftUI/CircularGaugeStyle
crawled: 2025-12-03T06:10:10Z
---

# CircularGaugeStyle

**Structure**

A gauge style that displays an open ring with a marker that appears at a point along the ring to indicate the gauge’s current value.

## Declaration

```swift
struct CircularGaugeStyle
```

## Overview

Use [circular](GaugeStyle/circular.zh-Hans.md) to construct this style.

## Creating the gauge style

- **init()**: Creates a circular gauge.
- **init(tint:)**: Creates a circular gauge that draws with a specified color.

## Supporting types

- **DefaultGaugeStyle**: The default gauge view style in the current context of the view being styled.
- **AccessoryCircularGaugeStyle**: A gauge style that displays an open ring with a marker that appears at a point along the ring to indicate the gauge’s current value.
- **AccessoryCircularCapacityGaugeStyle**: A gauge style that displays a closed ring that’s partially filled in to indicate the gauge’s current value.
- **LinearGaugeStyle**: A gauge style that displays a bar with a marker that appears at a point along the bar to indicate the gauge’s current value.
- **LinearCapacityGaugeStyle**: A gauge style that displays bar that fills from leading to trailing edges as the gauge’s current value increases.
- **AccessoryLinearGaugeStyle**: A gauge style that displays bar with a marker that appears at a point along the bar to indicate the gauge’s current value.
- **AccessoryLinearCapacityGaugeStyle**: A gauge style that displays bar that fills from leading to trailing edges as the gauge’s current value increases.

## Conforms To

- GaugeStyle

