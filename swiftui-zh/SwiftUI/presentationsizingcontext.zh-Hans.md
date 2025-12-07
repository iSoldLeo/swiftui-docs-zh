---
来源： https://developer.apple.com/documentation/swiftui/presentationsizingcontext
抓取时间： 2025-12-04T13:08:32Z
---

# PresentationSizingContext

**Structure**

有关演示文稿的上下文信息。

## 声明

```swift
struct PresentationSizingContext
```

## 概览

`PresentationSizingContext`的属性会影响演示文稿的大小。



## 调整演示文稿大小

- **presentationCompactAdaptation(horizontal:vertical:)**：指定如何使演示文稿适应水平和垂直紧凑的尺寸类别。
- **presentationCompactAdaptation(_:)**：指定如何使演示文稿适应紧凑的尺寸类别。
- **PresentationAdaptation**：将演示文稿调整为不同尺寸等级的策略。
- **presentationSizing(_:)**：设置包含演示文稿的大小。
- **PresentationSizing**：定义演示内容大小以及演示大小如何随内容大小变化而调整的类型。
- **PresentationSizingRoot**：为具有定义的演示文稿大小的演示文稿提供的视图代理。


---
source: https://developer.apple.com/documentation/swiftui/presentationsizingcontext
crawled: 2025-12-04T13:08:32Z
---

# PresentationSizingContext

**Structure**

Contextual information about a presentation.

## Declaration

```swift
struct PresentationSizingContext
```

## Overview

The properties of a `PresentationSizingContext` can influence what size is proposed to a presentation.



## Adapting a presentation size

- **presentationCompactAdaptation(horizontal:vertical:)**: Specifies how to adapt a presentation to horizontally and vertically compact size classes.
- **presentationCompactAdaptation(_:)**: Specifies how to adapt a presentation to compact size classes.
- **PresentationAdaptation**: Strategies for adapting a presentation to a different size class.
- **presentationSizing(_:)**: Sets the sizing of the containing presentation.
- **PresentationSizing**: A type that defines the size of the presentation content and how the presentation size adjusts to its content’s size changing.
- **PresentationSizingRoot**: A proxy to a view provided to the presentation with a defined presentation size.

