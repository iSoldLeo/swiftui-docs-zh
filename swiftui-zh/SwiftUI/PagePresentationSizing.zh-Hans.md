--- 来源：https://developer.apple.com/documentation/SwiftUI/PagePresentationSizing
抓取时间：2025-12-03T06:02:25Z

---

# PagePresentationSizing

**Structure**

页面大小大致相当于一张纸的大小，适合信息性或排版性内容。

## 声明

```swift
struct PagePresentationSizing
```

## 概述

在 iOS 上，`.page` 尺寸设置强制执行平台定义的垂直和水平尺寸下限。在 macOS 上，不强制执行下限，但会根据演示者的高度计算出建议的最大高度。要实现超出这些限制的演示，请参阅 `PresentationSizing.fitted` 或实现您自己的自定义 [PresentationSizing](PresentationSizing.zh-Hans.md)。

## 支持的类型

- **AutomaticPresentationSizing**：默认的展示尺寸，适合平台。

- **FittedPresentationSizing**：展示尺寸由内容的理想尺寸决定。

- **FormPresentationSizing**：尺寸适合表单，宽度略小于`.page`。

## 符合以下规范

- PresentationSizing

- Sendable

- SendableMetatype


---
source: https://developer.apple.com/documentation/SwiftUI/PagePresentationSizing
crawled: 2025-12-03T06:02:25Z
---

# PagePresentationSizing

**Structure**

The size is roughly the size of a page of paper, appropriate for informational or compositional content.

## Declaration

```swift
struct PagePresentationSizing
```

## Overview

On iOS, `.page` sizing enforces a platform-defined floor for the vertical and horizontal dimensions. On macOS, no floor is enforced, however a maximum proposed height is derived from the presenter height. To achieve presentations outside of these bounds, see `PresentationSizing.fitted` or implement your own custom [PresentationSizing](PresentationSizing.zh-Hans.md).



## Supporting types

- **AutomaticPresentationSizing**: The default presentation sizing, appropriate for the platform.
- **FittedPresentationSizing**: The size of the presentation is dictated by the ideal size of the content.
- **FormPresentationSizing**: The size is appropriate for forms and slightly less wide than`.page`

## Conforms To

- PresentationSizing
- Sendable
- SendableMetatype

