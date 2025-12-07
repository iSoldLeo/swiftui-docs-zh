---
来源： https://developer.apple.com/documentation/swiftui/edge/corner/style
抓取时间： 2025-12-05T22:21:32Z
---

# 边缘.边角.样式

**Structure**

矩形形状的每个角的样式。角的半径可以是固定的，也可以与容器形状同心。要创建具有可配置边角样式的形状，请调用[ConcentricRectangle](../../ConcentricRectangle.zh-Hans.md) 的初始化器之一并传入样式。

### 声明

```swift
struct Style
```

## 概览



## 类型属性

- **concentric**：同心角样式。当一个角与其容器同心时，它会调整当前角半径，以确保容器角半径等于当前角半径加上角之间的距离。

### 类型方法

- **concentric(minimum:)**：同心角样式，可选择最小角样式。当一个角与其容器同心时，它会调整当前角半径，以确保容器角半径等于当前角半径加上角之间的距离。如果当前角距离容器角太远，除非提供最小角样式，否则半径将被解析为零。
- **fixed(_:)**：固定半径的边角样式。

## 默认实现

- **ExpressibleByFloatLiteral 实现** **ExpressibleByIntegerLiteral Implementations
- **ExpressibleByIntegerLiteral 实现**

## 符合

- 可动画
- 可复制
- 等价
- 可通过浮点型字表达
- 可按整数表达
- 可散列
- 可发送
- 可发送元类型


---
source: https://developer.apple.com/documentation/swiftui/edge/corner/style
crawled: 2025-12-05T22:21:32Z
---

# Edge.Corner.Style

**Structure**

The per-corner style of a rectangular shape. A corner can be of fixed corner radius, or be concentric to the container shape. To create such a shape with configurable corner styles, call one of the initializers of [ConcentricRectangle](../../ConcentricRectangle.zh-Hans.md) and pass in the style.

## Declaration

```swift
struct Style
```

## Overview



## Type Properties

- **concentric**: The concentric corner style. When a corner is concentric to its container, it will adjust the current corner radius to ensure that the container corner radius equals to current corner radius plus the distance between corners.

## Type Methods

- **concentric(minimum:)**: The concentric corner style with an optional minimum corner style. When a corner is concentric to its container, it will adjust the current corner radius to ensure that the container corner radius equals to current corner radius plus the distance between corners. If the current corner is too far away from the container corner, the radius will be resolved as zero unless a minimum corner style is provided.
- **fixed(_:)**: The fixed radius corner style.

## Default Implementations

- **ExpressibleByFloatLiteral Implementations**
- **ExpressibleByIntegerLiteral Implementations**

## Conforms To

- Animatable
- Copyable
- Equatable
- ExpressibleByFloatLiteral
- ExpressibleByIntegerLiteral
- Hashable
- Sendable
- SendableMetatype

