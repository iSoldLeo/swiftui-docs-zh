--- 来源：https://developer.apple.com/documentation/swiftui/mixedimmersionstyle
抓取时间：2025-12-05T21:08:23Z

---

# MixedImmersionStyle

**Structure**

一种沉浸式风格，可将无边界内容与其他应用内容混合显示，并支持视频直通。

## 声明

```swift
struct MixedImmersionStyle
```

## 概述

选择此沉浸式风格后，[onImmersionChange(initial:_:)](View/onImmersionChange_initial.zh-Hans.md) 闭包报告的沉浸量为 `0.0`。

使用 [mixed](ImmersionStyle/mixed.zh-Hans.md) 和 [immersionStyle(selection:in:)](Scene/immersionStyle_selection_in.zh-Hans.md) 修饰符来指定此风格。

## 创建沉浸式风格

- **init()**

## 支持的类型

- **AutomaticImmersionStyle**：沉浸式空间的默认风格。

- **FullImmersionStyle**：一种显示无边界内容的沉浸式风格，完全取代了透传视频。

- **ProgressiveImmersionStyle**：一种显示无边界内容的沉浸式风格，部分取代了透传视频。

## 符合以下规范

- ImmersionStyle


---
source: https://developer.apple.com/documentation/swiftui/mixedimmersionstyle
crawled: 2025-12-05T21:08:23Z
---

# MixedImmersionStyle

**Structure**

An immersion style that displays unbounded content intermixed with other app content, along with passthrough video.

## Declaration

```swift
struct MixedImmersionStyle
```

## Overview

When this immersion style is selected, the immersion amount reported by the closure of [onImmersionChange(initial:_:)](View/onImmersionChange_initial.zh-Hans.md) is `0.0`.

Use [mixed](ImmersionStyle/mixed.zh-Hans.md) with the [immersionStyle(selection:in:)](Scene/immersionStyle_selection_in.zh-Hans.md)modifier to specify this style.

## Creating the immersion style

- **init()**

## Supporting types

- **AutomaticImmersionStyle**: The default style of immersive spaces.
- **FullImmersionStyle**: An immersion style that displays unbounded content that completely replaces passthrough video.
- **ProgressiveImmersionStyle**: An immersion style that displays unbounded content that partially replaces passthrough video.

## Conforms To

- ImmersionStyle

