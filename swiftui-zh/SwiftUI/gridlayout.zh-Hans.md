--- 来源：https://developer.apple.com/documentation/swiftui/gridlayout

抓取时间：2025-12-04T13:36:46Z

---

# GridLayout

**Structure**

一个可用于条件布局的网格。

## 声明

```swift
@frozen struct GridLayout
```

## 概述

此布局容器的行为类似于 [Grid](Grid.zh-Hans.md)，但遵循 [Layout](Layout.zh-Hans.md) 协议，因此您可以在使用 [AnyLayout](AnyLayout.zh-Hans.md) 构建的条件布局中使用它。如果您不需要条件布局，请改用 [Grid](Grid.zh-Hans.md)。

## 创建网格

- **init(alignment:horizontalSpacing:verticalSpacing:)**：创建具有指定间距和对齐方式的网格。

## 获取网格属性

- **alignment**：子视图的对齐方式。

- **horizontalSpacing**：相邻子视图之间的水平距离。

- **verticalSpacing**：相邻子视图之间的垂直距离。

## 类型别名

- **GridLayout.Body**

## 默认实现

- **布局实现**

## 布局类型转换

- **AnyLayout**：布局协议的类型擦除实例。

- **HStackLayout**：可在条件布局中使用的水平容器。

- **VStackLayout**：一个可用于条件布局的垂直容器。

- **ZStackLayout**：一个可用于条件布局的覆盖容器。

## 符合以下规则

- 可动画化

- 可按位复制

- 可复制

- 布局

- 可发送

- 可发送元类型


---
source: https://developer.apple.com/documentation/swiftui/gridlayout
crawled: 2025-12-04T13:36:46Z
---

# GridLayout

**Structure**

A grid that you can use in conditional layouts.

## Declaration

```swift
@frozen struct GridLayout
```

## Overview

This layout container behaves like a [Grid](Grid.zh-Hans.md), but conforms to the [Layout](Layout.zh-Hans.md) protocol so you can use it in the conditional layouts that you construct with [AnyLayout](AnyLayout.zh-Hans.md). If you don’t need a conditional layout, use [Grid](Grid.zh-Hans.md) instead.

## Creating a grid

- **init(alignment:horizontalSpacing:verticalSpacing:)**: Creates a grid with the specified spacing and alignment.

## Getting the grid’s properties

- **alignment**: The alignment of subviews.
- **horizontalSpacing**: The horizontal distance between adjacent subviews.
- **verticalSpacing**: The vertical distance between adjacent subviews.

## Type Aliases

- **GridLayout.Body**

## Default Implementations

- **Layout Implementations**

## Transitioning between layout types

- **AnyLayout**: A type-erased instance of the layout protocol.
- **HStackLayout**: A horizontal container that you can use in conditional layouts.
- **VStackLayout**: A vertical container that you can use in conditional layouts.
- **ZStackLayout**: An overlaying container that you can use in conditional layouts.

## Conforms To

- Animatable
- BitwiseCopyable
- Copyable
- Layout
- Sendable
- SendableMetatype

