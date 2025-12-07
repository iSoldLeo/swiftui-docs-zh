---
来源： https://developer.apple.com/documentation/SwiftUI/SymbolRenderingMode/monochrome
抓取时间： 2025-12-03T06:21:35Z
---

# 单色

**类型属性**

一种将符号渲染为单层并填充前景样式的模式。

## 声明

```swift
static let monochrome: SymbolRenderingMode
```

## 讨论

例如，您可以将填充的感叹号三角形渲染为紫色：

```swift
Image(systemName: "exclamationmark.triangle.fill")
    .symbolRenderingMode(.monochrome)
    .foregroundStyle(Color.purple)
```

## 获取符号渲染模式

- **hierarchical**：将符号渲染为多层的模式，前景样式采用不同的不透明度。
- **multicolor**：将符号渲染为具有继承样式的多个图层的模式。
- **palette**：将符号渲染为多个图层并在各图层上应用不同样式的模式。


---
source: https://developer.apple.com/documentation/SwiftUI/SymbolRenderingMode/monochrome
crawled: 2025-12-03T06:21:35Z
---

# monochrome

**Type Property**

A mode that renders symbols as a single layer filled with the foreground style.

## Declaration

```swift
static let monochrome: SymbolRenderingMode
```

## Discussion

For example, you can render a filled exclamation mark triangle in purple:

```swift
Image(systemName: "exclamationmark.triangle.fill")
    .symbolRenderingMode(.monochrome)
    .foregroundStyle(Color.purple)
```

## Getting symbol rendering modes

- **hierarchical**: A mode that renders symbols as multiple layers, with different opacities applied to the foreground style.
- **multicolor**: A mode that renders symbols as multiple layers with their inherit styles.
- **palette**: A mode that renders symbols as multiple layers, with different styles applied to the layers.

