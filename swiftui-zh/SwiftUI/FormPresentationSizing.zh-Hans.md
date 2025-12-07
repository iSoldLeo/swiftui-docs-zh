---
来源： https://developer.apple.com/documentation/SwiftUI/FormPresentationSizing
抓取时间： 2025-12-03T06:02:25Z
---

# 表单展示尺寸

**Structure**

大小适合表格，宽度略小于`.page`。

## 声明

```swift
struct FormPresentationSizing
```

## 概览

在 iOS 上，`.form` 大小会强制执行平台定义的垂直和水平尺寸的底线。在 macOS 上，没有执行底线，但会根据演示者的高度得出建议的最大高度。要实现超出这些界限的演示，请参阅`PresentationSizing.fitted` 或执行自己的自定义[PresentationSizing](PresentationSizing.zh-Hans.md)。



## 支持类型

- **AutomaticPresentationSizing**：适合平台的默认显示大小。
- **FittedPresentationSizing**：演示文稿的大小由内容的理想大小决定。
- **PagePresentationSizing**：大小大致相当于一页纸的大小，适合信息性或构成性内容。

## 符合

- 演示尺寸
- 可发送
- 可发送元类型


---
source: https://developer.apple.com/documentation/SwiftUI/FormPresentationSizing
crawled: 2025-12-03T06:02:25Z
---

# FormPresentationSizing

**Structure**

The size is appropriate for forms and slightly less wide than`.page`

## Declaration

```swift
struct FormPresentationSizing
```

## Overview

On iOS, `.form` sizing enforces a platform-defined floor for the vertical and horizontal dimensions. On macOS, no floor is enforced, however a maximum proposed height is derived from the presenter height. To achieve presentations outside of these bounds, see `PresentationSizing.fitted` or implement your own custom [PresentationSizing](PresentationSizing.zh-Hans.md).



## Supporting types

- **AutomaticPresentationSizing**: The default presentation sizing, appropriate for the platform.
- **FittedPresentationSizing**: The size of the presentation is dictated by the ideal size of the content.
- **PagePresentationSizing**: The size is roughly the size of a page of paper, appropriate for informational or compositional content.

## Conforms To

- PresentationSizing
- Sendable
- SendableMetatype

