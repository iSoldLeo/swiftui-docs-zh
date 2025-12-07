--- 来源：https://developer.apple.com/documentation/SwiftUI/SymbolRenderingMode
抓取时间：2025-12-02T17:35:56Z

---

# SymbolRenderingMode

**Structure**

符号渲染模式。

## 声明

```swift
struct SymbolRenderingMode
```

## 获取符号渲染模式

- **hierarchical**：将符号渲染为多个图层，并对每个图层的前景色应用不同的不透明度。

- **monochrome**：将符号渲染为单个图层，并填充前景色。

- **multicolor**：将符号渲染为多个图层，并应用其继承的样式。

- **palette**：一种将符号渲染为多个图层的模式，每个图层应用不同的样式。

## 设置符号渲染模式

- **symbolRenderingMode(_:)**：设置此视图中符号图像的渲染模式。

- **symbolRenderingMode**：当前符号渲染模式，或者 `nil` 表示使用当前图像和前景样式作为参数自动选择模式。

- **SymbolColorRenderingMode**：一种填充符号图像图层的方法。

- **SymbolVariableValueMode**：一种渲染符号图像变量值的方法。

## 符合以下标准

- Sendable

- SendableMetatype


---
source: https://developer.apple.com/documentation/SwiftUI/SymbolRenderingMode
crawled: 2025-12-02T17:35:56Z
---

# SymbolRenderingMode

**Structure**

A symbol rendering mode.

## Declaration

```swift
struct SymbolRenderingMode
```

## Getting symbol rendering modes

- **hierarchical**: A mode that renders symbols as multiple layers, with different opacities applied to the foreground style.
- **monochrome**: A mode that renders symbols as a single layer filled with the foreground style.
- **multicolor**: A mode that renders symbols as multiple layers with their inherit styles.
- **palette**: A mode that renders symbols as multiple layers, with different styles applied to the layers.

## Setting symbol rendering modes

- **symbolRenderingMode(_:)**: Sets the rendering mode for symbol images within this view.
- **symbolRenderingMode**: The current symbol rendering mode, or `nil` denoting that the mode is picked automatically using the current image and foreground style as parameters.
- **SymbolColorRenderingMode**: A method of filling a layer in a symbol image.
- **SymbolVariableValueMode**: A method of rendering the variable value of a symbol image.

## Conforms To

- Sendable
- SendableMetatype

