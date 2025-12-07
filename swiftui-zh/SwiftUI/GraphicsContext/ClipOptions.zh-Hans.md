---
来源： https://developer.apple.com/documentation/SwiftUI/GraphicsContext/ClipOptions
抓取时间：2025-12-02T20:58:19Z
---

# GraphicsContext.ClipOptions

**Structure**

影响剪贴图形使用的选项。

## 声明

```swift
@frozen struct ClipOptions
```

## 概览

调用 [clip(to:style:options:)](clip_to_style_options.zh-Hans.md) 将路径添加到剪辑形状数组时，或调用 [clipToLayer(opacity:options:content:)](clipToLayer_opacity_options_content.zh-Hans.md) 添加剪辑层时，使用这些选项可影响 SwiftUI 对剪辑形状的解释。

## 获取剪辑选项

- **inverse**：反转形状或图层 alpha 作为剪辑蒙版的选项。

## 遮罩

- **clip(to:style:options:)**：将路径添加到上下文的剪辑形状数组中。
- **clipToLayer(opacity:options:content:)**：将您在新图层中定义的剪辑形状添加到上下文的剪辑形状数组中。
- **clipBoundingRect**：当前用户空间中所有当前剪辑形状交集的边界矩形。

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
source: https://developer.apple.com/documentation/SwiftUI/GraphicsContext/ClipOptions
crawled: 2025-12-02T20:58:19Z
---

# GraphicsContext.ClipOptions

**Structure**

Options that affect the use of clip shapes.

## Declaration

```swift
@frozen struct ClipOptions
```

## Overview

Use these options to affect how SwiftUI interprets a clip shape when you call [clip(to:style:options:)](clip_to_style_options.zh-Hans.md) to add a path to the array of clip shapes, or when you call [clipToLayer(opacity:options:content:)](clipToLayer_opacity_options_content.zh-Hans.md) to add a clipping layer.

## Getting clip options

- **inverse**: An option to invert the shape or layer alpha as the clip mask.

## Masking

- **clip(to:style:options:)**: Adds a path to the context’s array of clip shapes.
- **clipToLayer(opacity:options:content:)**: Adds a clip shape that you define in a new layer to the context’s array of clip shapes.
- **clipBoundingRect**: The bounding rectangle of the intersection of all current clip shapes in the current user space.

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

