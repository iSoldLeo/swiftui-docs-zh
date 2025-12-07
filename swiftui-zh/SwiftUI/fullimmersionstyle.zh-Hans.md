--- 来源：https://developer.apple.com/documentation/swiftui/fullimmersionstyle
抓取时间：2025-12-05T21:08:23Z

---

# FullImmersionStyle

**Structure**

一种沉浸式样式，用于显示无边界内容，完全取代透传视频。

## 声明

```swift
struct FullImmersionStyle
```

## 概述

选择此沉浸式样式后，[onImmersionChange(initial:_:)](View/onImmersionChange_initial.zh-Hans.md) 闭包报告的沉浸量为 `1.0`。

使用 [full](ImmersionStyle/full.zh-Hans.md) 和 [immersionStyle(selection:in:)](Scene/immersionStyle_selection_in.zh-Hans.md) 修饰符来指定此样式。

## 创建沉浸式风格

- **init()**

## 支持的类型

- **AutomaticImmersionStyle**：沉浸式空间的默认风格。

- **MixedImmersionStyle**：一种沉浸式风格，它将无边界内容与其他应用内容混合显示，并包含透传视频。

- **ProgressiveImmersionStyle**：一种沉浸式风格，它显示无边界内容，并部分替换透传视频。

## 符合以下规范

- ImmersionStyle


---
source: https://developer.apple.com/documentation/swiftui/fullimmersionstyle
crawled: 2025-12-05T21:08:23Z
---

# FullImmersionStyle

**Structure**

An immersion style that displays unbounded content that completely replaces passthrough video.

## Declaration

```swift
struct FullImmersionStyle
```

## Overview

When this immersion style is selected, the immersion amount reported by the closure of [onImmersionChange(initial:_:)](View/onImmersionChange_initial.zh-Hans.md) is `1.0`.

Use [full](ImmersionStyle/full.zh-Hans.md) with the [immersionStyle(selection:in:)](Scene/immersionStyle_selection_in.zh-Hans.md)modifier to specify this style.

## Creating the immersion style

- **init()**

## Supporting types

- **AutomaticImmersionStyle**: The default style of immersive spaces.
- **MixedImmersionStyle**: An immersion style that displays unbounded content intermixed with other app content, along with passthrough video.
- **ProgressiveImmersionStyle**: An immersion style that displays unbounded content that partially replaces passthrough video.

## Conforms To

- ImmersionStyle

