--- 来源：https://developer.apple.com/documentation/SwiftUI/SymbolColorRenderingMode
抓取时间：2025-12-02T17:35:57Z

---

# SymbolColorRenderingMode

**Structure**

一种填充符号图像图层的方法。

## 声明

```swift
struct SymbolColorRenderingMode
```

## 类型属性

- **flat**：符号图像图层应填充纯色。

- **gradient**：符号图像图层应填充轴向渐变。

## 设置符号渲染模式

- **symbolRenderingMode(_:)**：设置此视图中符号图像的渲染模式。

- **symbolRenderingMode**：当前符号渲染模式，或 `nil`：表示使用当前图像和前景样式作为参数自动选择模式。

- **SymbolRenderingMode**：符号渲染模式。

- **SymbolVariableValueMode**：渲染符号图像变量值的方法。

## 符合以下标准

- Equatable

- Sendable

- SendableMetatype


---
source: https://developer.apple.com/documentation/SwiftUI/SymbolColorRenderingMode
crawled: 2025-12-02T17:35:57Z
---

# SymbolColorRenderingMode

**Structure**

A method of filling a layer in a symbol image.

## Declaration

```swift
struct SymbolColorRenderingMode
```

## Type Properties

- **flat**: The symbol image layer should be filled with a solid color.
- **gradient**: The symbol image layer should be filled with an axial gradient.

## Setting symbol rendering modes

- **symbolRenderingMode(_:)**: Sets the rendering mode for symbol images within this view.
- **symbolRenderingMode**: The current symbol rendering mode, or `nil` denoting that the mode is picked automatically using the current image and foreground style as parameters.
- **SymbolRenderingMode**: A symbol rendering mode.
- **SymbolVariableValueMode**: A method of rendering the variable value of a symbol image.

## Conforms To

- Equatable
- Sendable
- SendableMetatype

