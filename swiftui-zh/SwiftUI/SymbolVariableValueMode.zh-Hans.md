--- 来源：https://developer.apple.com/documentation/SwiftUI/SymbolVariableValueMode

抓取时间：2025-12-02T17:35:57Z

---

# SymbolVariableValueMode

**Structure**

一种渲染符号图像变量值的方法。

## 声明

```swift
struct SymbolVariableValueMode
```

## 类型属性

- **color**：“颜色”变量值模式。根据每个变量图层的阈值与当前值的比较情况，设置其不透明度为开启或关闭。

- **draw**：“绘制”变量值模式。根据每个变量图层的范围与当前值的关系，更改其绘制长度。

## 设置符号渲染模式

- **symbolRenderingMode(_:)**：设置此视图中符号图像的渲染模式。

- **symbolRenderingMode**：当前符号渲染模式，或 `nil`：表示使用当前图像和前景样式作为参数自动选择模式。

- **SymbolRenderingMode**：符号渲染模式。

- **SymbolColorRenderingMode**：符号图像中图层的填充方法。

## 符合以下标准

- Equatable

- Sendable

- SendableMetatype


---
source: https://developer.apple.com/documentation/SwiftUI/SymbolVariableValueMode
crawled: 2025-12-02T17:35:57Z
---

# SymbolVariableValueMode

**Structure**

A method of rendering the variable value of a symbol image.

## Declaration

```swift
struct SymbolVariableValueMode
```

## Type Properties

- **color**: The “color” variable value mode. Sets the opacity of each variable layer to either on or off depending on how its threshold compared to the current value.
- **draw**: The “draw” variable value mode. Changes the drawn length of each variable layer to either based on how its range relates to the current value.

## Setting symbol rendering modes

- **symbolRenderingMode(_:)**: Sets the rendering mode for symbol images within this view.
- **symbolRenderingMode**: The current symbol rendering mode, or `nil` denoting that the mode is picked automatically using the current image and foreground style as parameters.
- **SymbolRenderingMode**: A symbol rendering mode.
- **SymbolColorRenderingMode**: A method of filling a layer in a symbol image.

## Conforms To

- Equatable
- Sendable
- SendableMetatype

