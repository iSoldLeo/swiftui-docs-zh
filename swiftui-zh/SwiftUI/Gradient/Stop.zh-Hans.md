---
来源： https://developer.apple.com/documentation/SwiftUI/Gradient/Stop
抓取时间： 2025-12-03T06:25:35Z
---

# Gradient.Stop

**Structure**

渐变中的一个色块。

## 声明

```swift
@frozen struct Stop
```

## 创建渐变止点

- **init(color:location:)**：创建带有颜色和位置的色块。

## 配置渐变色色块

- **color**：色块的颜色。
- **location**：停止点的参数位置。

## 从停止点创建渐变效果

- **init(stops:)**：根据色站数组创建渐变效果。
- **stops**：色站数组。

## 符合

- 可复制
- 等价
- 可散列
- 可发送
- 可发送元类型


---
source: https://developer.apple.com/documentation/SwiftUI/Gradient/Stop
crawled: 2025-12-03T06:25:35Z
---

# Gradient.Stop

**Structure**

One color stop in the gradient.

## Declaration

```swift
@frozen struct Stop
```

## Creating a gradient stop

- **init(color:location:)**: Creates a color stop with a color and location.

## Configuring a gradient stop

- **color**: The color for the stop.
- **location**: The parametric location of the stop.

## Creating a gradient from stops

- **init(stops:)**: Creates a gradient from an array of color stops.
- **stops**: The array of color stops.

## Conforms To

- Copyable
- Equatable
- Hashable
- Sendable
- SendableMetatype

