---
来源： https://developer.apple.com/documentation/SwiftUI/FittedPresentationSizing
抓取时间： 2025-12-03T06:02:24Z
---

# FittedPresentationSizing

**Structure**

演示文稿的大小由内容的理想大小决定。

## 声明

```swift
struct FittedPresentationSizing
```

## 概览

演示文稿的横向和纵向尺寸均为`nil`。



## 支持类型

- **AutomaticPresentationSizing**：适合平台的默认显示大小。
- **FormPresentationSizing**：适合表单，宽度略小于`.page`。
- **PagePresentationSizing**：该尺寸大致相当于一页纸的大小，适用于信息或构图内容。

## 符合

- 演示尺寸
- 可发送
- 可发送元类型


---
source: https://developer.apple.com/documentation/SwiftUI/FittedPresentationSizing
crawled: 2025-12-03T06:02:24Z
---

# FittedPresentationSizing

**Structure**

The size of the presentation is dictated by the ideal size of the content.

## Declaration

```swift
struct FittedPresentationSizing
```

## Overview

The presentation is sized by proposing `nil` in the horizontal and vertical dimensions.



## Supporting types

- **AutomaticPresentationSizing**: The default presentation sizing, appropriate for the platform.
- **FormPresentationSizing**: The size is appropriate for forms and slightly less wide than`.page`
- **PagePresentationSizing**: The size is roughly the size of a page of paper, appropriate for informational or compositional content.

## Conforms To

- PresentationSizing
- Sendable
- SendableMetatype

