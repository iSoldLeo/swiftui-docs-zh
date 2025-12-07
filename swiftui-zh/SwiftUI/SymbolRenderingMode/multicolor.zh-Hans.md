---
来源： https://developer.apple.com/documentation/SwiftUI/SymbolRenderingMode/multicolor
抓取时间： 2025-12-03T06:21:36Z
---

# 多色

**类型属性**

一种模式，可将符号渲染为具有继承样式的多个图层。

## 声明

```swift
static let multicolor: SymbolRenderingMode
```

## 讨论

图层可以用其固有的样式或前景样式填充。例如，您可以使用其固有颜色来渲染一个填充感叹号的三角形，三角形为黄色，感叹号为白色：

```swift
Image(systemName: "exclamationmark.triangle.fill")
    .symbolRenderingMode(.multicolor)
```

## 获取符号渲染模式

- **hierarchical**：将符号渲染为多层的模式，前景样式采用不同的不透明度。
- **monochrome**：将符号渲染为单层并填充前景样式的模式。
- **palette**：将符号渲染为多个图层的模式，各图层应用不同的样式。


---
source: https://developer.apple.com/documentation/SwiftUI/SymbolRenderingMode/multicolor
crawled: 2025-12-03T06:21:36Z
---

# multicolor

**Type Property**

A mode that renders symbols as multiple layers with their inherit styles.

## Declaration

```swift
static let multicolor: SymbolRenderingMode
```

## Discussion

The layers may be filled with their own inherent styles, or the foreground style. For example, you can render a filled exclamation mark triangle in its inherent colors, with yellow for the triangle and white for the exclamation mark:

```swift
Image(systemName: "exclamationmark.triangle.fill")
    .symbolRenderingMode(.multicolor)
```

## Getting symbol rendering modes

- **hierarchical**: A mode that renders symbols as multiple layers, with different opacities applied to the foreground style.
- **monochrome**: A mode that renders symbols as a single layer filled with the foreground style.
- **palette**: A mode that renders symbols as multiple layers, with different styles applied to the layers.

