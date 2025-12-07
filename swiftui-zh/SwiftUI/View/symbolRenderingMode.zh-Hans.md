--- 来源：https://developer.apple.com/documentation/SwiftUI/View/symbolRenderingMode(_:)

抓取时间：2025-12-02T17:04:49Z

---

# symbolRenderingMode(_:)

**实例方法**

设置此视图中符号图像的渲染模式。

## 声明

```swift
nonisolated func symbolRenderingMode(_ mode: SymbolRenderingMode?) -> some View

```

## 参数

- **mode**：要使用的符号渲染模式。

## 返回值

使用您提供的渲染模式的视图。

## 设置符号渲染模式

- **symbolRenderingMode**：当前符号渲染模式，或者 `nil`：表示使用当前图像和前景样式作为参数自动选择模式。

- **SymbolRenderingMode**：符号渲染模式。

- **SymbolColorRenderingMode**：符号图像图层填充方法。

- **SymbolVariableValueMode**：符号图像变量值渲染方法。


---
source: https://developer.apple.com/documentation/SwiftUI/View/symbolRenderingMode(_:)
crawled: 2025-12-02T17:04:49Z
---

# symbolRenderingMode(_:)

**Instance Method**

Sets the rendering mode for symbol images within this view.

## Declaration

```swift
nonisolated func symbolRenderingMode(_ mode: SymbolRenderingMode?) -> some View

```

## Parameters

- **mode**: The symbol rendering mode to use.

## Return Value

A view that uses the rendering mode you supply.

## Setting symbol rendering modes

- **symbolRenderingMode**: The current symbol rendering mode, or `nil` denoting that the mode is picked automatically using the current image and foreground style as parameters.
- **SymbolRenderingMode**: A symbol rendering mode.
- **SymbolColorRenderingMode**: A method of filling a layer in a symbol image.
- **SymbolVariableValueMode**: A method of rendering the variable value of a symbol image.

