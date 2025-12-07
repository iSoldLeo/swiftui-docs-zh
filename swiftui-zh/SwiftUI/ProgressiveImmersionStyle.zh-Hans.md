--- 来源：https://developer.apple.com/documentation/SwiftUI/ProgressiveImmersionStyle
抓取时间：2025-12-03T05:33:24Z

---

# ProgressiveImmersionStyle

**Structure**

一种沉浸式样式，用于显示无边界内容，部分替换透传视频。

## 声明

```swift
struct ProgressiveImmersionStyle
```

## 概述

使用 [progressive](ImmersionStyle/progressive.zh-Hans.md) 和 [immersionStyle(selection:in:)](Scene/immersionStyle_selection_in.zh-Hans.md) 修饰符来指定此样式。

## 创建沉浸式样式

- **init()**：一种沉浸式样式，用于显示无边界内容，部分替换透传视频。

## 初始化器

- **init(immersion:initialAmount:)**：一种沉浸式样式，用于显示无边界内容，部分替代透传视频。

## 实例属性

- **aspectRatio**：此样式实例使用的宽高比。

- **initialImmersionAmount**：此样式实例使用的初始沉浸度。

- **maximumImmersionAmount**：此样式实例使用的最大沉浸度。

- **minimumImmersionAmount**：此样式实例使用的最小沉浸度。

## 支持类型

- **AutomaticImmersionStyle**：沉浸式空间的默认样式。

- **FullImmersionStyle**：一种沉浸式样式，用于显示无边界内容，完全替代透传视频。

- **MixedImmersionStyle**：一种沉浸式风格，可将无边界内容与其他应用内容混合显示，并支持视频穿透。

## 符合以下规范

- ImmersionStyle


---
source: https://developer.apple.com/documentation/SwiftUI/ProgressiveImmersionStyle
crawled: 2025-12-03T05:33:24Z
---

# ProgressiveImmersionStyle

**Structure**

An immersion style that displays unbounded content that partially replaces passthrough video.

## Declaration

```swift
struct ProgressiveImmersionStyle
```

## Overview

Use [progressive](ImmersionStyle/progressive.zh-Hans.md) with the [immersionStyle(selection:in:)](Scene/immersionStyle_selection_in.zh-Hans.md)modifier to specify this style.

## Creating the immersion style

- **init()**: An immersion style that displays unbounded content that partially replaces passthrough video.

## Initializers

- **init(immersion:initialAmount:)**: An immersion style that displays unbounded content that partially replaces passthrough video.

## Instance Properties

- **aspectRatio**: The aspect ratio used for this instance of the style.
- **initialImmersionAmount**: The initial amount of immersion used for this instance of the style.
- **maximumImmersionAmount**: The maximum amount of immersion used for this instance of the style.
- **minimumImmersionAmount**: The minimum amount of immersion used for this instance of the style.

## Supporting types

- **AutomaticImmersionStyle**: The default style of immersive spaces.
- **FullImmersionStyle**: An immersion style that displays unbounded content that completely replaces passthrough video.
- **MixedImmersionStyle**: An immersion style that displays unbounded content intermixed with other app content, along with passthrough video.

## Conforms To

- ImmersionStyle

