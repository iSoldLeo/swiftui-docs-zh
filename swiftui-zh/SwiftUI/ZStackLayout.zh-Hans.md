---
来源： https://developer.apple.com/documentation/SwiftUI/ZStackLayout
抓取时间： 2025-12-02T17:39:25Z
---

# ZStackLayout

**Structure**

可以在条件布局中使用的覆盖容器。

## 声明

```swift
@frozen struct ZStackLayout
```

## 概览

该布局容器的行为类似于 [ZStack](ZStack.zh-Hans.md)，但符合 [Layout](Layout.zh-Hans.md)协议，因此您可以在使用 [AnyLayout](AnyLayout.zh-Hans.md)构建的条件布局中使用它。如果不需要条件布局，请使用 [ZStack](ZStack.zh-Hans.md)。

## 创建堆栈

- **init(alignment:)**：以指定的对齐方式创建堆栈。

## 获取堆栈属性

- **alignment**：子视图的对齐方式。

## 在布局类型之间转换

- **AnyLayout**：布局协议的类型消除实例。
- **HStackLayout**：水平容器，可在条件布局中使用。
- **VStackLayout**：垂直容器，可在条件布局中使用。
- **GridLayout**：可以在条件布局中使用的网格。

## 符合

- 可动画
- 比特可复制
- 可复制
- 布局
- 可发送
- 可发送元类型


---
source: https://developer.apple.com/documentation/SwiftUI/ZStackLayout
crawled: 2025-12-02T17:39:25Z
---

# ZStackLayout

**Structure**

An overlaying container that you can use in conditional layouts.

## Declaration

```swift
@frozen struct ZStackLayout
```

## Overview

This layout container behaves like a [ZStack](ZStack.zh-Hans.md), but conforms to the [Layout](Layout.zh-Hans.md) protocol so you can use it in the conditional layouts that you construct with [AnyLayout](AnyLayout.zh-Hans.md). If you don’t need a conditional layout, use [ZStack](ZStack.zh-Hans.md) instead.

## Creating a stack

- **init(alignment:)**: Creates a stack with the specified alignment.

## Getting the stack’s properties

- **alignment**: The alignment of subviews.

## Transitioning between layout types

- **AnyLayout**: A type-erased instance of the layout protocol.
- **HStackLayout**: A horizontal container that you can use in conditional layouts.
- **VStackLayout**: A vertical container that you can use in conditional layouts.
- **GridLayout**: A grid that you can use in conditional layouts.

## Conforms To

- Animatable
- BitwiseCopyable
- Copyable
- Layout
- Sendable
- SendableMetatype

