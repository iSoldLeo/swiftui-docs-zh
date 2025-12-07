---
来源： https://developer.apple.com/documentation/SwiftUI/HighlightHoverEffect
抓取时间： 2025-12-03T06:45:37Z
---

# 高亮显示效果

**Structure**

一种悬停效果，可使用光源高亮显示视图以指示位置。

## 声明

```swift
struct HighlightHoverEffect
```

## 概览

您也可以使用 [highlight](CustomHoverEffect/highlight.zh-Hans.md) 构建这种悬停效果。

## 初始化器

- **init()**：创建高亮悬停效果。

## 支持类型

- **AutomaticHoverEffect**：基于周围环境的默认悬停效果。
- **EmptyHoverEffect**：用于构建附加效果的基本悬停效果。
- **LiftHoverEffect**：一种悬停效果，可将指针滑动到视图下方，并在视图缩放和获得阴影时消失。

## 符合

- 自定义悬停效果


---
source: https://developer.apple.com/documentation/SwiftUI/HighlightHoverEffect
crawled: 2025-12-03T06:45:37Z
---

# HighlightHoverEffect

**Structure**

A hover effect that highlights views using a light source to indicate position.

## Declaration

```swift
struct HighlightHoverEffect
```

## Overview

You can also use [highlight](CustomHoverEffect/highlight.zh-Hans.md) to construct this hover effect.

## Initializers

- **init()**: Creates a highlight hover effect.

## Supporting types

- **AutomaticHoverEffect**: The default hover effect based on the surrounding context.
- **EmptyHoverEffect**: A base hover effect used to build additional effects.
- **LiftHoverEffect**: A hover effect that slides the pointer under the view and disappears as the view scales up and gains a shadow.

## Conforms To

- CustomHoverEffect

