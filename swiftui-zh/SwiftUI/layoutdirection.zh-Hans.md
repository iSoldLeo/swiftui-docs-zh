--- 来源：https://developer.apple.com/documentation/swiftui/layoutdirection
抓取时间：2025-12-03T06:37:22Z

---

# LayoutDirection

**Enumeration**

SwiftUI 布局内容的方向。

## 声明

```swift
enum LayoutDirection
```

## 概述

SwiftUI 支持从左到右和从右到左两种布局方向，以支持不同的语言和区域设置。系统会根据用户的区域设置来设置该值，但您也可以使用 [environment(_:_:)](View/environment.zh-Hans.md) 修饰符来覆盖视图及其子视图的布局方向：

```swift
MyView()
    .environment(\.layoutDirection, .rightToLeft)
```

您还可以读取 [layoutDirection](EnvironmentValues/layoutDirection.zh-Hans.md) 环境变量值，以确定特定环境适用的布局方向。然而，在很多情况下，您无需根据此值执行任何操作。SwiftUI 会水平翻转每个视图在其父视图内的 x 坐标，因此布局计算会自动为两种模式生成所需的效果，无需任何更改。

## 获取布局方向

- **LayoutDirection.leftToRight**：从左到右的布局方向。

- **LayoutDirection.rightToLeft**：从右到左的布局方向。

## 创建布局方向

- **init(_:)**：根据其对应的 UITraitEnvironmentLayoutDirection 创建一个方向。

## 设置布局方向

- **layoutDirectionBehavior(_:)**：设置此视图在不同布局方向上的行为。

- **LayoutDirectionBehavior**：描述布局方向更改时应发生的情况。

- **layoutDirection**：与当前环境关联的布局方向。

- **LayoutRotationUnaryLayout**

## 符合以下标准

- CaseIterable

- Equatable

- Hashable

- Sendable

- SendableMetatype


---
source: https://developer.apple.com/documentation/swiftui/layoutdirection
crawled: 2025-12-03T06:37:22Z
---

# LayoutDirection

**Enumeration**

A direction in which SwiftUI can lay out content.

## Declaration

```swift
enum LayoutDirection
```

## Overview

SwiftUI supports both left-to-right and right-to-left directions for laying out content to support different languages and locales. The system sets the value based on the user’s locale, but you can also use the [environment(_:_:)](View/environment.zh-Hans.md) modifier to override the direction for a view and its child views:

```swift
MyView()
    .environment(\.layoutDirection, .rightToLeft)
```

You can also read the [layoutDirection](EnvironmentValues/layoutDirection.zh-Hans.md) environment value to find out which direction applies to a particular environment. However, in many cases, you don’t need to take any action based on this value. SwiftUI horizontally flips the x position of each view within its parent, so layout calculations automatically produce the desired effect for both modes without any changes.

## Getting layout directions

- **LayoutDirection.leftToRight**: A left-to-right layout direction.
- **LayoutDirection.rightToLeft**: A right-to-left layout direction.

## Creating a layout direction

- **init(_:)**: Create a direction from its UITraitEnvironmentLayoutDirection equivalent.

## Setting a layout direction

- **layoutDirectionBehavior(_:)**: Sets the behavior of this view for different layout directions.
- **LayoutDirectionBehavior**: A description of what should happen when the layout direction changes.
- **layoutDirection**: The layout direction associated with the current environment.
- **LayoutRotationUnaryLayout**

## Conforms To

- CaseIterable
- Equatable
- Hashable
- Sendable
- SendableMetatype

