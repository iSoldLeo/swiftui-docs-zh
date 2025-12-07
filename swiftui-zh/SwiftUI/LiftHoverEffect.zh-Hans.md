--- 来源：https://developer.apple.com/documentation/SwiftUI/LiftHoverEffect
抓取时间：2025-12-03T06:45:38Z

---

# LiftHoverEffect

**Structure**

一种悬停效果，指针会滑到视图下方，并在视图放大并获得阴影时消失。

## 声明

```swift
struct LiftHoverEffect
```

## 概述

您也可以使用 [lift](CustomHoverEffect/lift.zh-Hans.md) 来构建此悬停效果。

## 初始化器

- **init()**：创建提升悬停效果。

## 支持的类型

- **AutomaticHoverEffect**：基于周围上下文的默认悬停效果。

- **EmptyHoverEffect**：用于构建其他效果的基础悬停效果。

- **HighlightHoverEffect**：使用光源高亮显示视图以指示位置的悬停效果。

## 符合以下标准

- CustomHoverEffect


---
source: https://developer.apple.com/documentation/SwiftUI/LiftHoverEffect
crawled: 2025-12-03T06:45:38Z
---

# LiftHoverEffect

**Structure**

A hover effect that slides the pointer under the view and disappears as the view scales up and gains a shadow.

## Declaration

```swift
struct LiftHoverEffect
```

## Overview

You can also use [lift](CustomHoverEffect/lift.zh-Hans.md) to construct this hover effect.

## Initializers

- **init()**: Creates a lift hover effect.

## Supporting types

- **AutomaticHoverEffect**: The default hover effect based on the surrounding context.
- **EmptyHoverEffect**: A base hover effect used to build additional effects.
- **HighlightHoverEffect**: A hover effect that highlights views using a light source to indicate position.

## Conforms To

- CustomHoverEffect

