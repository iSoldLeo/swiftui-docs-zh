--- 来源：https://developer.apple.com/documentation/SwiftUI/Performance-analysis

抓取时间：2025-12-02T17:46:07Z

---

# 性能分析

衡量并提升应用的响应速度。

## 概述

使用 Instruments 检测应用中的卡顿和延迟，并分析耗时的视图主体更新以及频繁发生的 SwiftUI 更新，这些都可能导致卡顿和延迟。

## 要点

- **了解用户界面响应速度**：通过检查事件处理和渲染循环，提升应用的响应速度。

- **了解应用中的卡顿**：通过检查主线程和主运行循环，确定用户交互延迟的原因。

- **了解应用中的延迟**：通过检查渲染循环，确定应用运行中断的原因。

## 分析 SwiftUI 性能

- **理解并提升 SwiftUI 性能**：识别并解决耗时较长的视图更新问题，并降低更新频率。

## 工具支持

- **在 Xcode 中预览**：生成自定义视图的动态交互式预览。

- **Xcode 库自定义**：在 Xcode 库中公开自定义视图和修饰符。


---
source: https://developer.apple.com/documentation/SwiftUI/Performance-analysis
crawled: 2025-12-02T17:46:07Z
---

# Performance analysis

Measure and improve your app’s responsiveness.

## Overview

Use Instruments to detect hangs and hitches in your app, and to analyze long view body updates and frequently occurring SwiftUI updates that can contribute to hangs and hitches.

## Essentials

- **Understanding user interface responsiveness**: Make your app more responsive by examining the event-handling and rendering loop.
- **Understanding hangs in your app**: Determine the cause for delays in user interactions by examining the main thread and the main run loop.
- **Understanding hitches in your app**: Determine the cause of interruptions in motion by examining the render loop.

## Analyzing SwiftUI performance

- **Understanding and improving SwiftUI performance**: Identify and address long-running view updates, and reduce the frequency of updates.

## Tool support

- **Previews in Xcode**: Generate dynamic, interactive previews of your custom views.
- **Xcode library customization**: Expose custom views and modifiers in the Xcode library.

