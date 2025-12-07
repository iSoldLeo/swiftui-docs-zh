--- 来源：https://developer.apple.com/documentation/SwiftUI/PresentationAdaptation
抓取时间：2025-12-02T17:30:10Z

---

# PresentationAdaptation

**Structure**

用于将演示文稿适配到不同尺寸类别的策略。

## 声明

```swift
struct PresentationAdaptation
```

## 概述

将此类型的值与 [presentationCompactAdaptation(_:)](View/presentationCompactAdaptation.zh-Hans.md) 和 [presentationCompactAdaptation(horizontal:vertical:)](View/presentationCompactAdaptation_horizontal_vertical.zh-Hans.md) 修饰符一起使用。

## 获取适配策略

- **automatic**：使用默认的演示文稿适配。

- **none**：如果可能，不针对尺寸类别进行适配。

- **fullScreenCover**：调整尺寸时，首选全屏覆盖外观。

- **popover**：调整尺寸时，首选弹出式外观。

- **sheet**：调整尺寸时，首选工作表外观。

## 调整演示文稿尺寸

- **presentationCompactAdaptation(horizontal:vertical:)**：指定如何将演示文稿调整为水平和垂直方向的紧凑尺寸。

- **presentationCompactAdaptation(_:)**：指定如何将演示文稿调整为紧凑尺寸。

- **presentationSizing(_:)**：设置包含演示文稿的尺寸。

- **PresentationSizing**：定义演示文稿内容的尺寸以及演示文稿尺寸如何随内容尺寸变化而调整的类型。

- **PresentationSizingRoot**：指向已定义演示大小的视图的代理。

- **PresentationSizingContext**：关于演示的上下文信息。

## 符合以下标准

- Sendable

- SendableMetatype


---
source: https://developer.apple.com/documentation/SwiftUI/PresentationAdaptation
crawled: 2025-12-02T17:30:10Z
---

# PresentationAdaptation

**Structure**

Strategies for adapting a presentation to a different size class.

## Declaration

```swift
struct PresentationAdaptation
```

## Overview

Use values of this type with the [presentationCompactAdaptation(_:)](View/presentationCompactAdaptation.zh-Hans.md) and [presentationCompactAdaptation(horizontal:vertical:)](View/presentationCompactAdaptation_horizontal_vertical.zh-Hans.md) modifiers.

## Getting adaptation strategies

- **automatic**: Use the default presentation adaptation.
- **none**: Don’t adapt for the size class, if possible.
- **fullScreenCover**: Prefer a full-screen-cover appearance when adapting for size classes.
- **popover**: Prefer a popover appearance when adapting for size classes.
- **sheet**: Prefer a sheet appearance when adapting for size classes.

## Adapting a presentation size

- **presentationCompactAdaptation(horizontal:vertical:)**: Specifies how to adapt a presentation to horizontally and vertically compact size classes.
- **presentationCompactAdaptation(_:)**: Specifies how to adapt a presentation to compact size classes.
- **presentationSizing(_:)**: Sets the sizing of the containing presentation.
- **PresentationSizing**: A type that defines the size of the presentation content and how the presentation size adjusts to its content’s size changing.
- **PresentationSizingRoot**: A proxy to a view provided to the presentation with a defined presentation size.
- **PresentationSizingContext**: Contextual information about a presentation.

## Conforms To

- Sendable
- SendableMetatype

