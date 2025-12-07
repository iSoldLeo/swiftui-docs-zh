---
来源： https://developer.apple.com/documentation/SwiftUI/GraphicsContext/ResolvedText
抓取时间： 2025-12-02T20:58:15Z
---

# GraphicsContext.ResolvedText

**Structure**

解析到特定环境的文本视图。

## 声明

```swift
struct ResolvedText
```

## 概览

您可以手动调用 [doc://com.apple.SwiftUI/documentation/SwiftUI/GraphicsContext/resolve(_:)-4dx65] 或自动调用 [doc://com.apple.SwiftUI/documentation/SwiftUI/GraphicsContext/draw(_:in:)-5opqf] 或 [doc://com.apple.SwiftUI/documentation/SwiftUI/GraphicsContext/draw(_:at:anchor:)-5dgmd] 来解析[Text](../Text.zh-Hans.md)视图，以便将其绘制到上下文中。解析后的文本视图会考虑显示分辨率和当前配色方案等环境值。

## 获取文本属性

- **firstBaseline(in:)**：获取第一行升线到基线的距离。
- **lastBaseline(in:)**：获取第一行上升沿到最后一行基线的距离。
- **measure(in:)**：测量应放置文本的给定区域内已解析文本的大小。
- **shading**：用于填充未着色文本区域的阴影。

## 解析绘制的实体

- **resolve(_:)**：获取与图形上下文环境的当前值固定的图像版本。
- **resolveSymbol(id:)**：如果存在已识别的子视图，则以已解析符号的形式获取该视图。
- **GraphicsContext.ResolvedSymbol**：可多次绘制的静态绘制操作序列，保留其分辨率独立性。
- **GraphicsContext.ResolvedImage**：根据特定环境解析的图像。


---
source: https://developer.apple.com/documentation/SwiftUI/GraphicsContext/ResolvedText
crawled: 2025-12-02T20:58:15Z
---

# GraphicsContext.ResolvedText

**Structure**

A text view resolved to a particular environment.

## Declaration

```swift
struct ResolvedText
```

## Overview

You resolve a [Text](../Text.zh-Hans.md) view in preparation for drawing it into a context, either manually by calling [doc://com.apple.SwiftUI/documentation/SwiftUI/GraphicsContext/resolve(_:)-4dx65] or automatically when calling [doc://com.apple.SwiftUI/documentation/SwiftUI/GraphicsContext/draw(_:in:)-5opqf] or [doc://com.apple.SwiftUI/documentation/SwiftUI/GraphicsContext/draw(_:at:anchor:)-5dgmd]. The resolved text view takes into account environment values like the display resolution and current color scheme.

## Getting the text properties

- **firstBaseline(in:)**: Gets the distance from the first line’s ascender to its baseline.
- **lastBaseline(in:)**: Gets the distance from the first line’s ascender to the last line’s baseline.
- **measure(in:)**: Measures the size of the resolved text for a given area into which the text should be placed.
- **shading**: The shading to fill uncolored text regions with.

## Resolving a drawn entity

- **resolve(_:)**: Gets a version of an image that’s fixed with the current values of the graphics context’s environment.
- **resolveSymbol(id:)**: Gets the identified child view as a resolved symbol, if the view exists.
- **GraphicsContext.ResolvedSymbol**: A static sequence of drawing operations that may be drawn multiple times, preserving their resolution independence.
- **GraphicsContext.ResolvedImage**: An image resolved to a particular environment.

