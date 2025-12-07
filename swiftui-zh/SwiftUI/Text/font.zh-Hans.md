--- 来源：https://developer.apple.com/documentation/SwiftUI/Text/font(_:)

抓取时间：2025-12-01T02:39:10Z

---

# font(_:)

**实例方法**

设置视图中文本的默认字体。

## 声明

```swift
nonisolated func font(_ font: Font?) -> Text
```

## 参数

- **font**：显示此文本时使用的字体。

## 返回值

使用指定字体显示的文本。

## 说明

使用 `font(_:)` 将特定字体应用于单个文本视图，或应用于容器中的所有文本视图。

在下面的示例中，第一个文本字段直接设置了字体，而应用于后续容器的字体将应用于该容器内的所有文本视图：

```swift
VStack {
    Text("Font applied to a text view.")
        .font(.largeTitle)

    VStack {
        Text("These two text views have the same font")
        Text("applied to their parent view.")
    }
    .font(.system(size: 16, weight: .light, design: .default))
}
```

## 选择字体

- **fontWeight(_:)**：设置文本的字体粗细。

- **fontDesign(_:)**：设置文本的字体样式。

- **fontWidth(_:)**：设置文本的字体宽度。


---
source: https://developer.apple.com/documentation/SwiftUI/Text/font(_:)
crawled: 2025-12-01T02:39:10Z
---

# font(_:)

**Instance Method**

Sets the default font for text in the view.

## Declaration

```swift
nonisolated func font(_ font: Font?) -> Text
```

## Parameters

- **font**: The font to use when displaying this text.

## Return Value

Text that uses the font you specify.

## Discussion

Use `font(_:)` to apply a specific font to an individual Text View, or all of the text views in a container.

In the example below, the first text field has a font set directly, while the font applied to the following container applies to all of the text views inside that container:

```swift
VStack {
    Text("Font applied to a text view.")
        .font(.largeTitle)

    VStack {
        Text("These two text views have the same font")
        Text("applied to their parent view.")
    }
    .font(.system(size: 16, weight: .light, design: .default))
}
```



## Choosing a font

- **fontWeight(_:)**: Sets the font weight of the text.
- **fontDesign(_:)**: Sets the font design of the text.
- **fontWidth(_:)**: Sets the font width of the text.

