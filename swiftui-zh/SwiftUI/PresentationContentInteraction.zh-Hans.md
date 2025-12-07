---
来源： https://developer.apple.com/documentation/SwiftUI/PresentationContentInteraction
抓取时间：2025-12-02T17:30:18Z
---

# PresentationContentInteraction

**Structure**

一种行为，可用于影响演示如何响应轻扫手势。

## 声明

```swift
struct PresentationContentInteraction
```

## 概览

使用该类型的值时，应同时使用[presentationContentInteraction(_:)](View/presentationContentInteraction.zh-Hans.md)修饰符。

## 获取交互行为

- **automatic**：演示文稿的默认轻扫行为。
- **resizes**：在轻扫时优先调整演示文稿大小而不是滚动演示文稿内容的行为。
- **scrolls**：轻扫时优先滚动演示文稿内容而不是调整演示文稿大小的行为。

## 配置工作表的高度

- **presentationDetents(_:)**：设置附带工作表的可用制动器。
- **presentationDetents(_:selection:)**：为包围纸张设置可用的制动，使您可以对当前选择的制动进行编程控制。
- **presentationContentInteraction(_:)**：配置演示文稿上的轻扫手势行为。
- **presentationDragIndicator(_:)**：设置工作表顶部拖动指示器的可见性。
- **PresentationDetent**：表示工作表自然放置高度的类型。
- **CustomPresentationDetent**：自定义制动器的定义，其高度经过计算。

## 符合

- 等效
- 可发送
- 可发送元数据类型


---
source: https://developer.apple.com/documentation/SwiftUI/PresentationContentInteraction
crawled: 2025-12-02T17:30:18Z
---

# PresentationContentInteraction

**Structure**

A behavior that you can use to influence how a presentation responds to swipe gestures.

## Declaration

```swift
struct PresentationContentInteraction
```

## Overview

Use values of this type with the [presentationContentInteraction(_:)](View/presentationContentInteraction.zh-Hans.md) modifier.

## Getting interaction behaviors

- **automatic**: The default swipe behavior for the presentation.
- **resizes**: A behavior that prioritizes resizing a presentation when swiping, rather than scrolling the content of the presentation.
- **scrolls**: A behavior that prioritizes scrolling the content of a presentation when swiping, rather than resizing the presentation.

## Configuring a sheet’s height

- **presentationDetents(_:)**: Sets the available detents for the enclosing sheet.
- **presentationDetents(_:selection:)**: Sets the available detents for the enclosing sheet, giving you programmatic control of the currently selected detent.
- **presentationContentInteraction(_:)**: Configures the behavior of swipe gestures on a presentation.
- **presentationDragIndicator(_:)**: Sets the visibility of the drag indicator on top of a sheet.
- **PresentationDetent**: A type that represents a height where a sheet naturally rests.
- **CustomPresentationDetent**: The definition of a custom detent with a calculated height.

## Conforms To

- Equatable
- Sendable
- SendableMetatype

