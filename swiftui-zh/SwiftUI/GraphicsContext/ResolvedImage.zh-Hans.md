---
来源： https://developer.apple.com/documentation/SwiftUI/GraphicsContext/ResolvedImage
抓取时间： 2025-12-02T20:58:14Z
---

# GraphicsContext.ResolvedImage

**Structure**

解析到特定环境的图像。

## 声明

```swift
struct ResolvedImage
```

## 概览

您可以通过调用 [doc://com.apple.SwiftUI/documentation/SwiftUI/GraphicsContext/resolve(_:)-898z6] 手动解析[Image](../Image.zh-Hans.md)，或调用 [doc://com.apple.SwiftUI/documentation/SwiftUI/GraphicsContext/draw(_:in:style:)-blhz] 或 [doc://com.apple.SwiftUI/documentation/SwiftUI/GraphicsContext/draw(_:at:anchor:)-1z5wt] 自动解析[Image](../Image.zh-Hans.md)，为在上下文中绘制[Image](../Image.zh-Hans.md) 做准备。解析后的图像会考虑显示分辨率和当前配色方案等环境值。

## 获取图像属性

- **size**：图像的大小。
- **baseline**：图像顶部到基线的距离。
- **shading**：用于填充图像的可选阴影。

## 解析绘制的实体

- **resolve(_:)**：获取与图形上下文环境的当前值固定的图像版本。
- **resolveSymbol(id:)**：如果存在已识别的子视图，则以已解析符号的形式获取该视图。
- **GraphicsContext.ResolvedSymbol**：可多次绘制的静态绘制操作序列，保留其分辨率独立性。
- **GraphicsContext.ResolvedText**：解析到特定环境的文本视图。


---
source: https://developer.apple.com/documentation/SwiftUI/GraphicsContext/ResolvedImage
crawled: 2025-12-02T20:58:14Z
---

# GraphicsContext.ResolvedImage

**Structure**

An image resolved to a particular environment.

## Declaration

```swift
struct ResolvedImage
```

## Overview

You resolve an [Image](../Image.zh-Hans.md) in preparation for drawing it into a context, either manually by calling [doc://com.apple.SwiftUI/documentation/SwiftUI/GraphicsContext/resolve(_:)-898z6], or automatically when calling [doc://com.apple.SwiftUI/documentation/SwiftUI/GraphicsContext/draw(_:in:style:)-blhz] or [doc://com.apple.SwiftUI/documentation/SwiftUI/GraphicsContext/draw(_:at:anchor:)-1z5wt]. The resolved image takes into account environment values like the display resolution and current color scheme.

## Getting the image properties

- **size**: The size of the image.
- **baseline**: The distance from the top of the image to its baseline.
- **shading**: An optional shading to fill the image with.

## Resolving a drawn entity

- **resolve(_:)**: Gets a version of an image that’s fixed with the current values of the graphics context’s environment.
- **resolveSymbol(id:)**: Gets the identified child view as a resolved symbol, if the view exists.
- **GraphicsContext.ResolvedSymbol**: A static sequence of drawing operations that may be drawn multiple times, preserving their resolution independence.
- **GraphicsContext.ResolvedText**: A text view resolved to a particular environment.

