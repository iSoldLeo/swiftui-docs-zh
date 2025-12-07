---
来源： https://developer.apple.com/documentation/SwiftUI/GraphicsContext/GradientOptions
抓取时间： 2025-12-02T20:58:06Z
---

# GraphicsContext.GradientOptions

**Structure**

影响颜色渐变渲染的选项。

## 声明

```swift
@frozen struct GradientOptions
```

## 概览

使用这些选项可影响 SwiftUI 如何管理您为[Shading](Shading.zh-Hans.md) 实例创建并用于[GraphicsContext](../GraphicsContext.zh-Hans.md) 中的渐变。

## 获取渐变选项

- **linearColor**：在线性色彩空间中对颜色进行内插的选项。
- **mirror**：在标称范围外重复渐变的选项，每隔一个实例就会出现一次。
- **repeat**：在标称范围外重复梯度的选项。

## 绘制路径

- **stroke(_:with:lineWidth:)**：以指定的线宽在上下文中绘制路径。
- **stroke(_:with:style:)**：以指定的笔画样式在上下文中绘制路径。
- **fill(_:with:style:)**：在上下文中绘制路径并填充轮廓区域。
- **GraphicsContext.Shading**：用于勾画或填充路径的颜色或图案。

## 符合

- 比特可复制
- 可复制
- 等价
- 可表达数组原型
- 选项集
- 原始可表示
- 可发送
- 可发送元类
- 代数集


---
source: https://developer.apple.com/documentation/SwiftUI/GraphicsContext/GradientOptions
crawled: 2025-12-02T20:58:06Z
---

# GraphicsContext.GradientOptions

**Structure**

Options that affect the rendering of color gradients.

## Declaration

```swift
@frozen struct GradientOptions
```

## Overview

Use these options to affect how SwiftUI manages a gradient that you create for a [Shading](Shading.zh-Hans.md) instance for use in a [GraphicsContext](../GraphicsContext.zh-Hans.md).

## Getting gradient options

- **linearColor**: An option that interpolates between colors in a linear color space.
- **mirror**: An option that repeats the gradient outside its nominal range, reflecting every other instance.
- **repeat**: An option that repeats the gradient outside its nominal range.

## Drawing a path

- **stroke(_:with:lineWidth:)**: Draws a path into the context with a specified line width.
- **stroke(_:with:style:)**: Draws a path into the context with a specified stroke style.
- **fill(_:with:style:)**: Draws a path into the context and fills the outlined region.
- **GraphicsContext.Shading**: A color or pattern that you can use to outline or fill a path.

## Conforms To

- BitwiseCopyable
- Copyable
- Equatable
- ExpressibleByArrayLiteral
- OptionSet
- RawRepresentable
- Sendable
- SendableMetatype
- SetAlgebra

