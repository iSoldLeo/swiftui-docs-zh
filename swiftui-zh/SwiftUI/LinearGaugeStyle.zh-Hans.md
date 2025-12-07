--- 来源：https://developer.apple.com/documentation/SwiftUI/LinearGaugeStyle
抓取时间：2025-12-03T06:10:13Z

---

# LinearGaugeStyle

**Structure**

一种仪表样式，显示一个带有标记的条形图，该标记位于条形图上的某个点，用于指示仪表的当前值。

## 声明

```swift
struct LinearGaugeStyle
```

## 概述

使用 [linear](GaugeStyle/linear.zh-Hans.md) 构造此样式。

## 创建仪表样式

- **init()**：创建线性仪表样式。

## 已弃用的初始化器

- **init(tint:)**：创建带有色调的线性仪表样式。

## 支持的类型

- **DefaultGaugeStyle**：当前视图上下文中的默认仪表盘样式。

- **CircularGaugeStyle**：一种仪表盘样式，显示一个带有标记的开放圆环，该标记位于圆环上的某个点，用于指示仪表盘的当前值。

- **AccessoryCircularGaugeStyle**：一种仪表盘样式，显示一个带有标记的开放圆环，该标记位于圆环上的某个点，用于指示仪表盘的当前值。

- **AccessoryCircularCapacityGaugeStyle**：一种仪表盘样式，显示一个部分填充的闭合圆环，用于指示仪表盘的当前值。

- **LinearCapacityGaugeStyle**：一种仪表盘样式，显示一个条形图，该条形图会随着仪表盘当前值的增加而从前缘向后缘填充。

- **AccessoryLinearGaugeStyle**：一种仪表样式，其条形图上会显示一个标记，该标记位于条形图上的某个点，用于指示仪表的当前值。

- **AccessoryLinearCapacityGaugeStyle**：一种仪表样式，其条形图会随着仪表当前值的增加而从前缘填充到后缘。

## 符合以下规范

- GaugeStyle


---
source: https://developer.apple.com/documentation/SwiftUI/LinearGaugeStyle
crawled: 2025-12-03T06:10:13Z
---

# LinearGaugeStyle

**Structure**

A gauge style that displays a bar with a marker that appears at a point along the bar to indicate the gauge’s current value.

## Declaration

```swift
struct LinearGaugeStyle
```

## Overview

Use [linear](GaugeStyle/linear.zh-Hans.md) to construct this style.

## Creating the gauge style

- **init()**: Creates a linear gauge style.

## Deprecated initializers

- **init(tint:)**: Creates a linear gauge style with a tint color.

## Supporting types

- **DefaultGaugeStyle**: The default gauge view style in the current context of the view being styled.
- **CircularGaugeStyle**: A gauge style that displays an open ring with a marker that appears at a point along the ring to indicate the gauge’s current value.
- **AccessoryCircularGaugeStyle**: A gauge style that displays an open ring with a marker that appears at a point along the ring to indicate the gauge’s current value.
- **AccessoryCircularCapacityGaugeStyle**: A gauge style that displays a closed ring that’s partially filled in to indicate the gauge’s current value.
- **LinearCapacityGaugeStyle**: A gauge style that displays bar that fills from leading to trailing edges as the gauge’s current value increases.
- **AccessoryLinearGaugeStyle**: A gauge style that displays bar with a marker that appears at a point along the bar to indicate the gauge’s current value.
- **AccessoryLinearCapacityGaugeStyle**: A gauge style that displays bar that fills from leading to trailing edges as the gauge’s current value increases.

## Conforms To

- GaugeStyle

