---
来源： https://developer.apple.com/documentation/SwiftUI/GraphicsContext/ResolvedSymbol
抓取时间： 2025-12-02T20:58:13Z
---

# GraphicsContext.ResolvedSymbol

**Structure**

可多次绘制的静态绘制操作序列，保留其分辨率独立性。

## 声明

```swift
struct ResolvedSymbol
```

## 概览

调用 [resolveSymbol(id:)](resolveSymbol_id.zh-Hans.md) 可解析子视图，以便将其绘制到上下文中。解析后的视图会考虑显示分辨率和当前配色方案等环境值。

## 获取符号属性

- **size**：解析后符号的尺寸。

## 解析绘制的实体

- **resolve(_:)**：获取与图形上下文环境的当前值固定的图像版本。
- **resolveSymbol(id:)**：如果存在已识别的子视图，则以已解析符号的形式获取该视图。
- **GraphicsContext.ResolvedImage**：解析到特定环境的图像。
- **GraphicsContext.ResolvedText**：解析到特定环境的文本视图。


---
source: https://developer.apple.com/documentation/SwiftUI/GraphicsContext/ResolvedSymbol
crawled: 2025-12-02T20:58:13Z
---

# GraphicsContext.ResolvedSymbol

**Structure**

A static sequence of drawing operations that may be drawn multiple times, preserving their resolution independence.

## Declaration

```swift
struct ResolvedSymbol
```

## Overview

You resolve a child view in preparation for drawing it into a context by calling [resolveSymbol(id:)](resolveSymbol_id.zh-Hans.md). The resolved view takes into account environment values like the display resolution and current color scheme.

## Getting the symbol properties

- **size**: The dimensions of the resolved symbol.

## Resolving a drawn entity

- **resolve(_:)**: Gets a version of an image that’s fixed with the current values of the graphics context’s environment.
- **resolveSymbol(id:)**: Gets the identified child view as a resolved symbol, if the view exists.
- **GraphicsContext.ResolvedImage**: An image resolved to a particular environment.
- **GraphicsContext.ResolvedText**: A text view resolved to a particular environment.

