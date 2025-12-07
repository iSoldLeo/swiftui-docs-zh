---
来源： https://developer.apple.com/documentation/SwiftUI/SymbolRenderingMode/palette
抓取时间： 2025-12-03T06:21:37Z
---

# 调色板

**类型属性**

一种模式，可将符号渲染为多个图层，并在图层上应用不同的样式。

## 声明

```swift
static let palette: SymbolRenderingMode
```

## 讨论

在此模式下，SwiftUI 会将图像中每个连续定义的图层映射到前景样式的一级、二级和三级变体中的下一个。您可以使用 [foregroundStyle(_:_:)](../View/foregroundStyle.zh-Hans.md) 和 [foregroundStyle(_:_:_:)](../View/foregroundStyle.zh-Hans.md) 修饰符明确指定这些样式。如果只指定一个主要前景样式，SwiftUI 会自动从该样式派生其他样式。例如，您可以使用黄色作为感叹号的色调，并使用青色填充三角形，从而呈现填充的感叹号三角形：

```swift
Image(systemName: "exclamationmark.triangle.fill")
    .symbolRenderingMode(.palette)
    .foregroundStyle(Color.yellow, Color.cyan)
```

您也可以省略符号渲染模式，因为指定多个前景样式意味着要切换到调色板渲染模式：

```swift
Image(systemName: "exclamationmark.triangle.fill")
    .foregroundStyle(Color.yellow, Color.cyan)
```

## 获取符号渲染模式

- **hierarchical**：将符号渲染为多层的模式，前景样式采用不同的不透明度。
- **monochrome**：将符号渲染为单层并填充前景样式的模式。
- **multicolor**：将符号渲染为具有继承样式的多个图层的模式。


---
source: https://developer.apple.com/documentation/SwiftUI/SymbolRenderingMode/palette
crawled: 2025-12-03T06:21:37Z
---

# palette

**Type Property**

A mode that renders symbols as multiple layers, with different styles applied to the layers.

## Declaration

```swift
static let palette: SymbolRenderingMode
```

## Discussion

In this mode SwiftUI maps each successively defined layer in the image to the next of the primary, secondary, and tertiary variants of the foreground style. You can specify these styles explicitly using the [foregroundStyle(_:_:)](../View/foregroundStyle.zh-Hans.md) and [foregroundStyle(_:_:_:)](../View/foregroundStyle.zh-Hans.md) modifiers. If you only specify a primary foreground style, SwiftUI automatically derives the others from that style. For example, you can render a filled exclamation mark triangle with yellow as the tint color for the exclamation mark, and fill the triangle with cyan:

```swift
Image(systemName: "exclamationmark.triangle.fill")
    .symbolRenderingMode(.palette)
    .foregroundStyle(Color.yellow, Color.cyan)
```

You can also omit the symbol rendering mode, as specifying multiple foreground styles implies switching to palette rendering mode:

```swift
Image(systemName: "exclamationmark.triangle.fill")
    .foregroundStyle(Color.yellow, Color.cyan)
```

## Getting symbol rendering modes

- **hierarchical**: A mode that renders symbols as multiple layers, with different opacities applied to the foreground style.
- **monochrome**: A mode that renders symbols as a single layer filled with the foreground style.
- **multicolor**: A mode that renders symbols as multiple layers with their inherit styles.

