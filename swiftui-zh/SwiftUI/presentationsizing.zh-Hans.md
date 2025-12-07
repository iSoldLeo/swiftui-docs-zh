--- 来源：https://developer.apple.com/documentation/swiftui/presentationsizing

抓取时间：2025-12-04T13:08:23Z

---

# PresentationSizing

**Protocol**

定义演示文稿内容大小以及演示文稿大小如何随内容大小变化而调整的类型。

## 声明

```swift
protocol PresentationSizing
```

## 概述

您无需定义此协议的自定义版本。系统提供的 [form](PresentationSizing/form.zh-Hans.md)、[page](PresentationSizing/page.zh-Hans.md) 和 [fitted](PresentationSizing/fitted.zh-Hans.md) 实现是便捷的，可自动适应不同的设备和屏幕尺寸。如果您确实想要自定义尺寸，请先考虑使用修饰符 `PresenationSizing/sticky(horizontal:vertical:)` 和 [fitted(horizontal:vertical:)](PresentationSizing/fitted_horizontal_vertical.zh-Hans.md)。例如，要定义一个 400x400 的正方形尺寸，可以使用以下修饰符：

```swift
protocol SquareSizing: PresentationSizing {
    func proposedSize(
        for subview: PresentationSizingRoot,
        context: PresentationSizingContext
    ) {
        .init(width: 400, height: 400)
    }
}

extension PresentationSizing where Self == SquareSizing {
    public static var square: Self { SquareSizing() }
}
```

然后，在调用点，您可以像修改系统尺寸一样修改 `.square`，例如，使其垂直适应内容：

```swift
.presentationSizing(.square.fitted(horizontal: false, vertical: true))
```

## 获取内置显示尺寸

- **automatic**：适用于平台的默认显示尺寸。

- **fitted**：展示尺寸由内容的理想尺寸决定。

- **form**：尺寸适用于表单，宽度略小于`.page`。

- **page**：尺寸与纸张大小大致相同，适用于信息性或排版性内容。

## 创建自定义展示尺寸

- **fitted(horizontal:vertical:)**

- **proposedSize(for:context:)**

- **sticky(horizontal:vertical:)**：将自身调整为在指定尺寸内保持固定——会不断增大，但不会缩小。

## 支持的类型

- **AutomaticPresentationSizing**：适用于平台的默认展示尺寸。

- **FittedPresentationSizing**：演示文稿的尺寸取决于内容的理想尺寸。

- **FormPresentationSizing**：此尺寸适用于表单，宽度略小于`.page`。

- **PagePresentationSizing**：此尺寸大致相当于一张纸的大小，适用于信息性或排版性内容。

## 调整演示文稿尺寸

- **presentationCompactAdaptation(horizontal:vertical:)**：指定如何将演示文稿调整为水平和垂直方向的紧凑尺寸类别。

- **presentationCompactAdaptation(_:)**：指定如何将演示文稿调整为紧凑尺寸类别。

- **PresentationAdaptation**：将演示文稿调整为不同尺寸类别的策略。

- **presentationSizing(_:)**：设置包含演示文稿的尺寸。

- **PresentationSizingRoot**：为具有已定义演示尺寸的演示文稿提供的视图代理。

- **PresentationSizingContext**：关于演示文稿的上下文信息。

## 符合规范的类型

- AutomaticPresentationSizing

- FittedPresentationSizing

- FormPresentationSizing

- PagePresentationSizing


---
source: https://developer.apple.com/documentation/swiftui/presentationsizing
crawled: 2025-12-04T13:08:23Z
---

# PresentationSizing

**Protocol**

A type that defines the size of the presentation content and how the presentation size adjusts to its content’s size changing.

## Declaration

```swift
protocol PresentationSizing
```

## Overview

You don’t need to define your own version of this protocol. The system implementations of [form](PresentationSizing/form.zh-Hans.md), [page](PresentationSizing/page.zh-Hans.md), and [fitted](PresentationSizing/fitted.zh-Hans.md) are conveniences that automatically adapt to different device and screen sizes. If you do want to define your own sizing, first consider using the modifiers `PresenationSizing/sticky(horizontal:vertical:)` and [fitted(horizontal:vertical:)](PresentationSizing/fitted_horizontal_vertical.zh-Hans.md). For example, to define your own sizing that proposes a 400x400 square size:

```swift
protocol SquareSizing: PresentationSizing {
    func proposedSize(
        for subview: PresentationSizingRoot,
        context: PresentationSizingContext
    ) {
        .init(width: 400, height: 400)
    }
}

extension PresentationSizing where Self == SquareSizing {
    public static var square: Self { SquareSizing() }
}
```

Then, at the callsite, you can modify `.square` just like system sizings, for example, to fit its content vertically:

```swift
.presentationSizing(.square.fitted(horizontal: false, vertical: true))
```



## Getting built-in presentation size

- **automatic**: The default presentation sizing, appropriate for the platform.
- **fitted**: The presentation sizing is dictated by the ideal size of the content
- **form**: The size is appropriate for forms and slightly less wide than`.page`
- **page**: The size is roughly the size of a page of paper, appropriate for informational or compositional content.

## Creating custom presentation size

- **fitted(horizontal:vertical:)**
- **proposedSize(for:context:)**
- **sticky(horizontal:vertical:)**: Modifies self to be sticky in the specified dimensions — growing, but not shrinking.

## Supporting types

- **AutomaticPresentationSizing**: The default presentation sizing, appropriate for the platform.
- **FittedPresentationSizing**: The size of the presentation is dictated by the ideal size of the content.
- **FormPresentationSizing**: The size is appropriate for forms and slightly less wide than`.page`
- **PagePresentationSizing**: The size is roughly the size of a page of paper, appropriate for informational or compositional content.

## Adapting a presentation size

- **presentationCompactAdaptation(horizontal:vertical:)**: Specifies how to adapt a presentation to horizontally and vertically compact size classes.
- **presentationCompactAdaptation(_:)**: Specifies how to adapt a presentation to compact size classes.
- **PresentationAdaptation**: Strategies for adapting a presentation to a different size class.
- **presentationSizing(_:)**: Sets the sizing of the containing presentation.
- **PresentationSizingRoot**: A proxy to a view provided to the presentation with a defined presentation size.
- **PresentationSizingContext**: Contextual information about a presentation.

## Conforming Types

- AutomaticPresentationSizing
- FittedPresentationSizing
- FormPresentationSizing
- PagePresentationSizing

