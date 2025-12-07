--- 来源：https://developer.apple.com/documentation/SwiftUI/View/monospacedDigit()

抓取时间：2025-11-30T21:20:03Z

---

# monospacedDigit()

**实例方法**

尽可能将所有子视图的字体设置为等宽数字，同时保持其他字符按比例缩放。

## 声明

```swift
nonisolated func monospacedDigit() -> some View

```

## 返回值

返回一个视图，其子视图的字体使用等宽数字，其他字符按比例缩放。

## 说明

使用等宽数字可以轻松地将相同大小的数字对齐，形成类似表格的排列。此功能也称为“表格数字”。

此修饰符仅影响数字字符，其他字符保持不变。

以下示例展示了 `monospacedDigit()` 对多个子视图的影响。该示例包含两个位于 [HStack](../HStack.zh-Hans.md) 内的 [VStack](../VStack.zh-Hans.md) 视图。每个 `VStack` 视图又包含两个 [Button](../Button.zh-Hans.md) 视图，其中第二个 `VStack` 视图对其内容应用了 `monospacedDigit()` 修饰符。因此，尾部 `VStack` 视图中按钮上的数字宽度相同，进而使按钮宽度相等。

```swift
var body: some View {
    HStack(alignment: .top) {
        VStack(alignment: .leading) {
            Button("Delete 111 messages") {}
            Button("Delete 222 messages") {}
        }
        VStack(alignment: .leading) {
            Button("Delete 111 messages") {}
            Button("Delete 222 messages") {}
        }
        .monospacedDigit()
    }
    .padding()
    .navigationTitle("monospacedDigit() Child Views")
}
```

如果子视图的基础字体不支持等宽数字，则字体保持不变。

## 控制文本样式

- **bold(_:)**：为该视图中的文本应用粗体。

- **italic(_:)**：为该视图中的文本应用斜体。

- **underline(_:pattern:color:)**：为该视图中的文本应用下划线。

- **strikethrough(_:pattern:color:)**：为该视图中的文本应用删除线。

- **textCase(_:)**：设置该视图中文本显示时的大小写转换。

- **textCase**：使用环境语言设置，覆盖 `Text` 的大小写转换样式。

- **monospaced(_:)**：尽可能将所有子视图的字体修改为当前字体的等宽变体。

- **AttributedTextFormattingDefinition**：用于定义视图中文本样式的协议。

- **AttributedTextValueConstraint**：用于定义特定属性值约束的协议。

- **AttributedTextFormatting**：与属性文本格式定义相关的类型的命名空间。


---
source: https://developer.apple.com/documentation/SwiftUI/View/monospacedDigit()
crawled: 2025-11-30T21:20:03Z
---

# monospacedDigit()

**Instance Method**

Modifies the fonts of all child views to use fixed-width digits, if possible, while leaving other characters proportionally spaced.

## Declaration

```swift
nonisolated func monospacedDigit() -> some View

```

## Return Value

A view whose child views’ fonts use fixed-width numeric characters, while leaving other characters proportionally spaced.

## Discussion

Using fixed-width digits allows you to easily align numbers of the same size in a table-like arrangement. This feature is also known as “tabular figures” or “tabular numbers.”

This modifier only affects numeric characters, and leaves all other characters unchanged.

The following example shows the effect of `monospacedDigit()` on multiple child views. The example consists of two [VStack](../VStack.zh-Hans.md) views inside an [HStack](../HStack.zh-Hans.md). Each `VStack` contains two [Button](../Button.zh-Hans.md) views, with the second `VStack` applying the `monospacedDigit()` modifier to its contents. As a result, the digits in the buttons in the trailing `VStack` are the same width, which in turn gives the buttons equal widths.

```swift
var body: some View {
    HStack(alignment: .top) {
        VStack(alignment: .leading) {
            Button("Delete 111 messages") {}
            Button("Delete 222 messages") {}
        }
        VStack(alignment: .leading) {
            Button("Delete 111 messages") {}
            Button("Delete 222 messages") {}
        }
        .monospacedDigit()
    }
    .padding()
    .navigationTitle("monospacedDigit() Child Views")
}
```



If a child view’s base font doesn’t support fixed-width digits, the font remains unchanged.

## Controlling text style

- **bold(_:)**: Applies a bold font weight to the text in this view.
- **italic(_:)**: Applies italics to the text in this view.
- **underline(_:pattern:color:)**: Applies an underline to the text in this view.
- **strikethrough(_:pattern:color:)**: Applies a strikethrough to the text in this view.
- **textCase(_:)**: Sets a transform for the case of the text contained in this view when displayed.
- **textCase**: A stylistic override to transform the case of `Text` when displayed, using the environment’s locale.
- **monospaced(_:)**: Modifies the fonts of all child views to use the fixed-width variant of the current font, if possible.
- **AttributedTextFormattingDefinition**: A protocol for defining how text can be styled in a view.
- **AttributedTextValueConstraint**: A protocol for defining a constraint on the value of a certain attribute.
- **AttributedTextFormatting**: A namespace for types related to attributed text formatting definitions.

