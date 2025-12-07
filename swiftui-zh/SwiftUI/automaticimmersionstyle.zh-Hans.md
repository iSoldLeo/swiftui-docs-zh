--- 来源：https://developer.apple.com/documentation/swiftui/automaticimmersionstyle
抓取时间：2025-12-05T21:08:22Z

---

# AutomaticImmersionStyle

**Structure**

沉浸式空间的默认样式。

## 声明

```swift
struct AutomaticImmersionStyle
```

## 概述

通常情况下，您无需显式使用此样式，但如果需要，请使用 [automatic](ImmersionStyle/automatic.zh-Hans.md) 和 [immersionStyle(selection:in:)](Scene/immersionStyle_selection_in.zh-Hans.md) 修饰符来指定此样式。

## 创建沉浸式样式

- **init()**

## 支持的类型

- **FullImmersionStyle**：一种显示无边界内容的沉浸式样式，可完全替代透传视频。

- **MixedImmersionStyle**：一种沉浸式风格，可将无边界内容与其他应用内容混合显示，并包含透传视频。

- **ProgressiveImmersionStyle**：一种沉浸式风格，可将无边界内容部分替换透传视频。

## 符合以下规范

- ImmersionStyle


---
source: https://developer.apple.com/documentation/swiftui/automaticimmersionstyle
crawled: 2025-12-05T21:08:22Z
---

# AutomaticImmersionStyle

**Structure**

The default style of immersive spaces.

## Declaration

```swift
struct AutomaticImmersionStyle
```

## Overview

You don’t typically use this style explicitly, but if you need to, use [automatic](ImmersionStyle/automatic.zh-Hans.md) with the [immersionStyle(selection:in:)](Scene/immersionStyle_selection_in.zh-Hans.md)modifier to specify this style.

## Creating the immersion style

- **init()**

## Supporting types

- **FullImmersionStyle**: An immersion style that displays unbounded content that completely replaces passthrough video.
- **MixedImmersionStyle**: An immersion style that displays unbounded content intermixed with other app content, along with passthrough video.
- **ProgressiveImmersionStyle**: An immersion style that displays unbounded content that partially replaces passthrough video.

## Conforms To

- ImmersionStyle

