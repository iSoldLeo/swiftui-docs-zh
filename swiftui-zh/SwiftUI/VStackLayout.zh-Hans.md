---
来源： https://developer.apple.com/documentation/SwiftUI/VStackLayout
抓取时间： 2025-12-02T16:03:46Z
---

# VStackLayout

**Structure**

垂直容器，可在条件布局中使用。

## 声明

```swift
@frozen struct VStackLayout
```

## 概览

该布局容器的行为类似于 [VStack](VStack.zh-Hans.md)，但符合 [Layout](Layout.zh-Hans.md)协议，因此您可以在使用 [AnyLayout](AnyLayout.zh-Hans.md)构建的条件布局中使用它。如果不需要条件布局，请使用 [VStack](VStack.zh-Hans.md)。

## 创建垂直堆栈

- **init(alignment:spacing:)**：以指定的间距和水平对齐方式创建垂直堆栈。

## 获取堆栈属性

- **alignment**：子视图的水平对齐方式。
- **spacing**：相邻子视图之间的距离。

## 在布局类型间转换

- **AnyLayout**：布局协议的类型消除实例。
- **HStackLayout**：水平容器，可在条件布局中使用。
- **ZStackLayout**：可以在条件布局中使用的覆盖容器。
- **GridLayout**：可在条件布局中使用的网格。

## 符合

- 可动画
- 比特可复制
- 可复制
- 布局
- 可发送
- 可发送元类型


---
source: https://developer.apple.com/documentation/SwiftUI/VStackLayout
crawled: 2025-12-02T16:03:46Z
---

# VStackLayout

**Structure**

A vertical container that you can use in conditional layouts.

## Declaration

```swift
@frozen struct VStackLayout
```

## Overview

This layout container behaves like a [VStack](VStack.zh-Hans.md), but conforms to the [Layout](Layout.zh-Hans.md) protocol so you can use it in the conditional layouts that you construct with [AnyLayout](AnyLayout.zh-Hans.md). If you don’t need a conditional layout, use [VStack](VStack.zh-Hans.md) instead.

## Creating a vertical stack

- **init(alignment:spacing:)**: Creates a vertical stack with the specified spacing and horizontal alignment.

## Getting the stack’s properties

- **alignment**: The horizontal alignment of subviews.
- **spacing**: The distance between adjacent subviews.

## Transitioning between layout types

- **AnyLayout**: A type-erased instance of the layout protocol.
- **HStackLayout**: A horizontal container that you can use in conditional layouts.
- **ZStackLayout**: An overlaying container that you can use in conditional layouts.
- **GridLayout**: A grid that you can use in conditional layouts.

## Conforms To

- Animatable
- BitwiseCopyable
- Copyable
- Layout
- Sendable
- SendableMetatype

