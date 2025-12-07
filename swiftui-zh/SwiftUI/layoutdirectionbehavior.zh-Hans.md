--- 来源：https://developer.apple.com/documentation/swiftui/layoutdirectionbehavior
抓取时间：2025-12-03T06:37:20Z

---

# LayoutDirectionBehavior

**Enumeration**

描述布局方向改变时应发生的情况。

## 声明

```swift
enum LayoutDirectionBehavior
```

## 概述

`LayoutDirectionBehavior` 可以与 `layoutDirectionBehavior` 视图修饰符或 `Shape` 的 `layoutDirectionBehavior` 属性一起使用。

## 获取行为

- **LayoutDirectionBehavior.fixed**：布局方向改变时不会镜像的行为。

- **mirrors**：布局方向为从右到左时的行为。

- **LayoutDirectionBehavior.mirrors(in:)**：布局方向具有指定值时的行为。

## 设置布局方向

- **layoutDirectionBehavior(_:)**：设置此视图在不同布局方向上的行为。

- **layoutDirection**：与当前环境关联的布局方向。

- **LayoutDirection**：SwiftUI 可以布局内容的方向。

- **LayoutRotationUnaryLayout**

## 符合以下协议

- Equatable

- Hashable

- Sendable

- SendableMetatype


---
source: https://developer.apple.com/documentation/swiftui/layoutdirectionbehavior
crawled: 2025-12-03T06:37:20Z
---

# LayoutDirectionBehavior

**Enumeration**

A description of what should happen when the layout direction changes.

## Declaration

```swift
enum LayoutDirectionBehavior
```

## Overview

A `LayoutDirectionBehavior` can be used with the `layoutDirectionBehavior` view modifier or the `layoutDirectionBehavior` property of `Shape`.

## Getting behaviors

- **LayoutDirectionBehavior.fixed**: A behavior that doesn’t mirror when the layout direction changes.
- **mirrors**: A behavior that mirrors when the layout direction is right-to-left.
- **LayoutDirectionBehavior.mirrors(in:)**: A behavior that mirrors when the layout direction has the specified value.

## Setting a layout direction

- **layoutDirectionBehavior(_:)**: Sets the behavior of this view for different layout directions.
- **layoutDirection**: The layout direction associated with the current environment.
- **LayoutDirection**: A direction in which SwiftUI can lay out content.
- **LayoutRotationUnaryLayout**

## Conforms To

- Equatable
- Hashable
- Sendable
- SendableMetatype

