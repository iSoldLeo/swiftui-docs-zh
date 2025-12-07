---
来源： https://developer.apple.com/documentation/SwiftUI/AutomaticHoverEffect
抓取时间： 2025-12-03T06:45:35Z
---

# 自动悬停效果

**Structure**

基于周围环境的默认悬停效果。

## 声明

```swift
struct AutomaticHoverEffect
```

## 概览

自动效果将解析为应用于当前视图层次结构的任何[defaultHoverEffect(_:)](View/defaultHoverEffect.zh-Hans.md)，如果没有定义默认效果，则解析为系统定义的效果。

您也可以使用[automatic](CustomHoverEffect/automatic.zh-Hans.md) 来构建这种悬停效果。

## 初始化器

- **init()**：创建自动悬停效果。

## 支持类型

- **EmptyHoverEffect**：用于创建附加效果的基本悬停效果。
- **HighlightHoverEffect**：一种悬停效果，可通过光源指示位置来突出显示视图。
- **LiftHoverEffect**：一种悬停效果，可将指针滑动到视图下方，并随着视图的缩放和阴影的增加而消失。

## 符合

- 自定义悬停效果


---
source: https://developer.apple.com/documentation/SwiftUI/AutomaticHoverEffect
crawled: 2025-12-03T06:45:35Z
---

# AutomaticHoverEffect

**Structure**

The default hover effect based on the surrounding context.

## Declaration

```swift
struct AutomaticHoverEffect
```

## Overview

The automatic effect will resolve to any [defaultHoverEffect(_:)](View/defaultHoverEffect.zh-Hans.md) applied to the current View hierarchy, or a system-defined effect if no default effect has been defined.

You can also use [automatic](CustomHoverEffect/automatic.zh-Hans.md) to construct this hover effect.

## Initializers

- **init()**: Creates an automatic hover effect.

## Supporting types

- **EmptyHoverEffect**: A base hover effect used to build additional effects.
- **HighlightHoverEffect**: A hover effect that highlights views using a light source to indicate position.
- **LiftHoverEffect**: A hover effect that slides the pointer under the view and disappears as the view scales up and gains a shadow.

## Conforms To

- CustomHoverEffect

