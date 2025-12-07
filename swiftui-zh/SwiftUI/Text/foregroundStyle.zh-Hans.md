--- 来源：https://developer.apple.com/documentation/SwiftUI/Text/foregroundStyle(_:)

抓取时间：2025-12-01T02:39:13Z

---

# foregroundStyle(_:)

**实例方法**

设置此视图显示的文本样式。

## 声明

```swift
nonisolated func foregroundStyle<S>(_ style: S) -> Text where S : ShapeStyle
```

## 参数

- **style**：显示此文本时要使用的样式。

## 返回值

一个使用您提供的颜色值的文本视图。

## 说明

使用此方法更改文本视图渲染的文本样式。

例如，您可以分别以红色、绿色和蓝色显示它们的名称：

```swift
HStack {
    Text("Red").foregroundStyle(.red)
    Text("Green").foregroundStyle(.green)
    Text("Blue").foregroundStyle(.blue)
}
```

## 设置视图文本样式

- **bold()**：为文本字体添加粗体或强调效果。

- **bold(_:)**：为文本添加粗体字。

- **italic()**：为文本添加斜体。

- **italic(_:)**：为文本添加斜体。

- **strikethrough(_:color:)**：为文本添加删除线。

- **strikethrough(_:pattern:color:)**：为文本添加删除线。

- **underline(_:color:)**：为文本添加下划线。

- **underline(_:pattern:color:)**：为文本添加下划线。

- **monospaced(_:)**：尽可能将文本字体修改为当前字体的等宽版本。

- **monospacedDigit()**：将文本视图的字体修改为使用等宽数字，同时保持其他字符按比例间距排列。

- **kerning(_:)**：设置字符间距（字距调整）。

- **tracking(_:)**：设置文本的字距。

- **baselineOffset(_:)**：设置文本相对于基线的垂直偏移量。

- **Text.Case**：用于转换文本中字符大小写的方案。

- **Text.DateStyle**：用于显示 `Date` 的预定义样式。


---
source: https://developer.apple.com/documentation/SwiftUI/Text/foregroundStyle(_:)
crawled: 2025-12-01T02:39:13Z
---

# foregroundStyle(_:)

**Instance Method**

Sets the style of the text displayed by this view.

## Declaration

```swift
nonisolated func foregroundStyle<S>(_ style: S) -> Text where S : ShapeStyle
```

## Parameters

- **style**: The style to use when displaying this text.

## Return Value

A text view that uses the color value you supply.

## Discussion

Use this method to change the rendering style of the text rendered by a text view.

For example, you can display the names of the colors red, green, and blue in their respective colors:

```swift
HStack {
    Text("Red").foregroundStyle(.red)
    Text("Green").foregroundStyle(.green)
    Text("Blue").foregroundStyle(.blue)
}
```



## Styling the view’s text

- **bold()**: Applies a bold or emphasized treatment to the fonts of the text.
- **bold(_:)**: Applies a bold font weight to the text.
- **italic()**: Applies italics to the text.
- **italic(_:)**: Applies italics to the text.
- **strikethrough(_:color:)**: Applies a strikethrough to the text.
- **strikethrough(_:pattern:color:)**: Applies a strikethrough to the text.
- **underline(_:color:)**: Applies an underline to the text.
- **underline(_:pattern:color:)**: Applies an underline to the text.
- **monospaced(_:)**: Modifies the font of the text to use the fixed-width variant of the current font, if possible.
- **monospacedDigit()**: Modifies the text view’s font to use fixed-width digits, while leaving other characters proportionally spaced.
- **kerning(_:)**: Sets the spacing, or kerning, between characters.
- **tracking(_:)**: Sets the tracking for the text.
- **baselineOffset(_:)**: Sets the vertical offset for the text relative to its baseline.
- **Text.Case**: A scheme for transforming the capitalization of characters within text.
- **Text.DateStyle**: A predefined style used to display a `Date`.

