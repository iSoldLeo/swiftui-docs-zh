---
来源：https://developer.apple.com/documentation/SwiftUI/TextEditor/init(text:selection:)
抓取时间：2025-11-30T21:36:43Z
---

# init(text:selection:)

**Initializer**

创建样式化文本编辑器。

## 声明

```swift
init(text: Binding<AttributedString>, selection: Binding<AttributedTextSelection>? = nil)
```

## 参数

- **text**：[Binding](../Binding.zh-Hans.md)，指向包含要编辑的样式文本的变量。
- **selection**：一个可选的[Binding](../Binding.zh-Hans.md)，指向包含选中内容的变量。

## 讨论

使用[TextEditor](../TextEditor.zh-Hans.md) 实例创建一个视图，用户可以在其中输入和编辑长格式文本。

在本例中，文本编辑器被设置为编辑样式文本：

```swift
struct StyledTextEditingView: View {
    @State private var text =
        AttributedString("This is some editable text...")

    var body: some View {
        TextEditor(text: $text)
    }
}
```

### 通过组合属性和视图修饰符来格式化文本

如果属性字符串（AttributedString）没有为给定范围的文本指定字体和/或前景色，富文本编辑器将为该范围的文本使用从环境中继承的字体和/或前景色，就像[doc://com.apple.SwiftUI/documentation/SwiftUI/Text/init(_:)-1a4oh]一样。要控制编辑器中可用的格式选项，请使用 [AttributedTextFormattingDefinition](../AttributedTextFormattingDefinition.zh-Hans.md) 协议。



### 使用选择绑定创建自定义控件

使用 [AttributedTextSelection](../AttributedTextSelection.zh-Hans.md) 实现自定义控件，例如应用粗体等格式：

```swift
struct StyledTextEditingView: View {
    @State private var text: AttributedString = ""
    @State private var selection = AttributedTextSelection()

    @Environment(\.fontResolutionContext) private var fontResolutionContext

    var body: some View {
        TextEditor(text: $text, selection: $selection)
            .toolbar {
                // A toggle controlling whether the current selection in the
                // editor has bold font.
                Toggle(
                    "Toggle Boldness",
                    systemImage: "bold",
                    isOn: Binding(get: {
                        // Get the font for the current selection.
                        let font = selection.typingAttributes(in: text).font
                        // Resolve the font in the current environment.
                        let resolved = (font ?? .default).resolve(in: fontResolutionContext)
                        // Return whether the resolved font is bold.
                        return resolved.isBold
                    }, set: { isBold in
                        // Update each run in the current selection, including
                        // the typing attributes, to reflect the new `isBold`
                        // value.
                        text.transformAttributes(in: &selection) {
                            // Override the boldness of the font. If no font is
                            // present, use `Font.default` for the effective
                            // environment font as the basis.
                            $0.font = ($0.font ?? .default).bold(isBold)
                        }
                    })
                )
            }
    }
}
```






---
source: https://developer.apple.com/documentation/SwiftUI/TextEditor/init(text:selection:)
crawled: 2025-11-30T21:36:43Z
---

# init(text:selection:)

**Initializer**

Creates a styled text editor.

## Declaration

```swift
init(text: Binding<AttributedString>, selection: Binding<AttributedTextSelection>? = nil)
```

## Parameters

- **text**: A [Binding](../Binding.zh-Hans.md) to the variable containing the styled text to edit.
- **selection**: An optional [Binding](../Binding.zh-Hans.md) to the variable containing the selection.

## Discussion

Use a [TextEditor](../TextEditor.zh-Hans.md) instance to create a view in which users can enter and edit long-form styled text.

In this example the text editor is setup to edit styled text:

```swift
struct StyledTextEditingView: View {
    @State private var text =
        AttributedString("This is some editable text...")

    var body: some View {
        TextEditor(text: $text)
    }
}
```

### Format text by combining attributes and view modifiers

If the AttributedString does not have a font and/or foreground color specified for a given range of text, the rich text editor will use the font and/or foreground color inherited from the environment for that range of text, just like [doc://com.apple.SwiftUI/documentation/SwiftUI/Text/init(_:)-1a4oh]. To control what formatting options are available in the editor, use the [AttributedTextFormattingDefinition](../AttributedTextFormattingDefinition.zh-Hans.md) protocol.



### Build custom controls using the selection binding

Use [AttributedTextSelection](../AttributedTextSelection.zh-Hans.md) for implementing custom controls, e.g. for applying formatting such as boldness:

```swift
struct StyledTextEditingView: View {
    @State private var text: AttributedString = ""
    @State private var selection = AttributedTextSelection()

    @Environment(\.fontResolutionContext) private var fontResolutionContext

    var body: some View {
        TextEditor(text: $text, selection: $selection)
            .toolbar {
                // A toggle controlling whether the current selection in the
                // editor has bold font.
                Toggle(
                    "Toggle Boldness",
                    systemImage: "bold",
                    isOn: Binding(get: {
                        // Get the font for the current selection.
                        let font = selection.typingAttributes(in: text).font
                        // Resolve the font in the current environment.
                        let resolved = (font ?? .default).resolve(in: fontResolutionContext)
                        // Return whether the resolved font is bold.
                        return resolved.isBold
                    }, set: { isBold in
                        // Update each run in the current selection, including
                        // the typing attributes, to reflect the new `isBold`
                        // value.
                        text.transformAttributes(in: &selection) {
                            // Override the boldness of the font. If no font is
                            // present, use `Font.default` for the effective
                            // environment font as the basis.
                            $0.font = ($0.font ?? .default).bold(isBold)
                        }
                    })
                )
            }
    }
}
```





