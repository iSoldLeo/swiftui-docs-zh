---
来源： https://developer.apple.com/documentation/SwiftUI/SymbolRenderingMode/hierarchical
抓取时间： 2025-12-03T06:21:35Z
---

# 分级

**类型属性**

一种将符号渲染为多个图层的模式，前景样式采用不同的不透明度。

## 声明

```swift
static let hierarchical: SymbolRenderingMode
```

## 讨论

SwiftUI 会使用前景样式填充第一层，并使用前景样式的二级和三级变体填充其他层。您可以使用 [foregroundStyle(_:_:)](../View/foregroundStyle.zh-Hans.md) 和 [foregroundStyle(_:_:_:)](../View/foregroundStyle.zh-Hans.md) 修饰符明确指定这些样式。如果只指定一个主要前景样式，SwiftUI 会自动从该样式派生其他样式。例如，您可以使用紫色作为感叹号的着色，并使用不透明度较低的紫色来呈现填充的三角形感叹号：

```swift
Image(systemName: "exclamationmark.triangle.fill")
    .symbolRenderingMode(.hierarchical)
    .foregroundStyle(Color.purple)
```

## 获取符号渲染模式

- **monochrome**：将符号渲染为单层并填充前景样式的模式。
- **multicolor**：将符号渲染为具有继承样式的多个图层的模式。
- **palette**：将符号渲染为多个图层并在各图层上应用不同样式的模式。


---
source: https://developer.apple.com/documentation/SwiftUI/SymbolRenderingMode/hierarchical
crawled: 2025-12-03T06:21:35Z
---

# hierarchical

**Type Property**

A mode that renders symbols as multiple layers, with different opacities applied to the foreground style.

## Declaration

```swift
static let hierarchical: SymbolRenderingMode
```

## Discussion

SwiftUI fills the first layer with the foreground style, and the others the secondary, and tertiary variants of the foreground style. You can specify these styles explicitly using the [foregroundStyle(_:_:)](../View/foregroundStyle.zh-Hans.md) and [foregroundStyle(_:_:_:)](../View/foregroundStyle.zh-Hans.md) modifiers. If you only specify a primary foreground style, SwiftUI automatically derives the others from that style. For example, you can render a filled exclamation mark triangle with purple as the tint color for the exclamation mark, and lower opacity purple for the triangle:

```swift
Image(systemName: "exclamationmark.triangle.fill")
    .symbolRenderingMode(.hierarchical)
    .foregroundStyle(Color.purple)
```

## Getting symbol rendering modes

- **monochrome**: A mode that renders symbols as a single layer filled with the foreground style.
- **multicolor**: A mode that renders symbols as multiple layers with their inherit styles.
- **palette**: A mode that renders symbols as multiple layers, with different styles applied to the layers.

