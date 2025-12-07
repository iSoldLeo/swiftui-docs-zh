--- 来源：https://developer.apple.com/documentation/SwiftUI/PresentationBackgroundInteraction
抓取时间：2025-12-02T17:30:22Z

---

# PresentationBackgroundInteraction

**Structure**

演示文稿背后的视图可用的交互类型。

## 声明

```swift
struct PresentationBackgroundInteraction
```

## 概述

将此类型的值与 [presentationBackgroundInteraction(_:)](View/presentationBackgroundInteraction.zh-Hans.md) 修饰符一起使用。

## 获取交互类型

- **automatic**：演示文稿的默认背景交互。

- **disabled**：用户无法与演示文稿背后的视图进行交互。

- **enabled**：用户可以与演示文稿背后的视图进行交互。

- **enabled(upThrough:)**：用户可以通过指定的深度与演示文稿背后的视图进行交互。

## 设置工作表及其背景的样式

- **presentationCornerRadius(_:)**：请求演示文稿具有特定的圆角半径。

- **presentationBackground(_:)**：使用形状样式设置包含工作表的演示文稿背景。

- **presentationBackground(alignment:content:)**：将包含工作表的演示文稿背景设置为自定义视图。

- **presentationBackgroundInteraction(_:)**：控制用户是否可以与演示文稿背后的视图进行交互。

## 符合以下规范

- Sendable

- SendableMetatype


---
source: https://developer.apple.com/documentation/SwiftUI/PresentationBackgroundInteraction
crawled: 2025-12-02T17:30:22Z
---

# PresentationBackgroundInteraction

**Structure**

The kinds of interaction available to views behind a presentation.

## Declaration

```swift
struct PresentationBackgroundInteraction
```

## Overview

Use values of this type with the [presentationBackgroundInteraction(_:)](View/presentationBackgroundInteraction.zh-Hans.md) modifier.

## Getting interaction types

- **automatic**: The default background interaction for the presentation.
- **disabled**: People can’t interact with the view behind a presentation.
- **enabled**: People can interact with the view behind a presentation.
- **enabled(upThrough:)**: People can interact with the view behind a presentation up through a specified detent.

## Styling a sheet and its background

- **presentationCornerRadius(_:)**: Requests that the presentation have a specific corner radius.
- **presentationBackground(_:)**: Sets the presentation background of the enclosing sheet using a shape style.
- **presentationBackground(alignment:content:)**: Sets the presentation background of the enclosing sheet to a custom view.
- **presentationBackgroundInteraction(_:)**: Controls whether people can interact with the view behind a presentation.

## Conforms To

- Sendable
- SendableMetatype

