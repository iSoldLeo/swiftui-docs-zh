---
来源： https://developer.apple.com/documentation/SwiftUI/GraphicsContext/resolve(_:)
抓取时间： 2025-12-02T20:58:11Z
---

# resolve(_:)

**实例方法**

获取根据图形上下文环境的当前值固定的图像版本。

## 声明

```swift
func resolve(_ image: Image) -> GraphicsContext.ResolvedImage
```

## 参数

- **image**：要解析的[Image](../Image.zh-Hans.md)。

## 返回值

解析到当前上下文环境中的图像，并考虑显示分辨率和当前配色方案等环境值。

## 讨论

您可以通过查看图像的 [size](ResolvedImage/size.zh-Hans.md) 和 [baseline](ResolvedImage/baseline.zh-Hans.md) 属性来测量解析后的图像。您可以使用上下文的[doc://com.apple.SwiftUI/documentation/SwiftUI/GraphicsContext/draw(_:in:style:)-7rvee] 或[doc://com.apple.SwiftUI/documentation/SwiftUI/GraphicsContext/draw(_:at:anchor:)-1z5wt] 方法绘制解析后的图像。

## 解析绘制的实体

- **resolveSymbol(id:)**：如果存在已识别的子视图，则以已解析符号的形式获取该视图。
- **GraphicsContext.ResolvedSymbol**：可多次绘制的静态绘制操作序列，保留其分辨率独立性。
- **GraphicsContext.ResolvedImage**：根据特定环境解析的图像。
- **GraphicsContext.ResolvedText**：解析到特定环境的文本视图。


---
source: https://developer.apple.com/documentation/SwiftUI/GraphicsContext/resolve(_:)
crawled: 2025-12-02T20:58:11Z
---

# resolve(_:)

**Instance Method**

Gets a version of an image that’s fixed with the current values of the graphics context’s environment.

## Declaration

```swift
func resolve(_ image: Image) -> GraphicsContext.ResolvedImage
```

## Parameters

- **image**: The [Image](../Image.zh-Hans.md) to resolve.

## Return Value

An image that’s resolved into the current context’s environment, taking into account environment values like the display resolution and current color scheme.

## Discussion

You can measure the resolved image by looking at its [size](ResolvedImage/size.zh-Hans.md) and [baseline](ResolvedImage/baseline.zh-Hans.md) properties. You can draw the resolved image with the context’s [doc://com.apple.SwiftUI/documentation/SwiftUI/GraphicsContext/draw(_:in:style:)-7rvee] or [doc://com.apple.SwiftUI/documentation/SwiftUI/GraphicsContext/draw(_:at:anchor:)-1z5wt] method.

## Resolving a drawn entity

- **resolveSymbol(id:)**: Gets the identified child view as a resolved symbol, if the view exists.
- **GraphicsContext.ResolvedSymbol**: A static sequence of drawing operations that may be drawn multiple times, preserving their resolution independence.
- **GraphicsContext.ResolvedImage**: An image resolved to a particular environment.
- **GraphicsContext.ResolvedText**: A text view resolved to a particular environment.

