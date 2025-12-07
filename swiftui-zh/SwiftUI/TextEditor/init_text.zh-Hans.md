---
来源：https://developer.apple.com/documentation/SwiftUI/TextEditor/init(text:)
抓取时间：2025-12-02T17:51:54Z
---

# init(text:)

**Initializer**

创建纯文本编辑器。

## 声明

```swift
init(text: Binding<String>)
```

## 参数

- **text**：[Binding](../Binding.zh-Hans.md)，指向包含要编辑文本的变量。

## 讨论

使用[TextEditor](../TextEditor.zh-Hans.md) 实例创建一个视图，用户可以在其中输入和编辑长文本。

在本例中，文本编辑器使用 13 点 Helvetica Neue 字体和每行 5 点间距渲染灰色文本：

```swift
struct TextEditingView: View {
    @State private var fullText: String = "This is some editable text..."

    var body: some View {
        TextEditor(text: $fullText)
            .foregroundColor(Color.gray)
            .font(.custom("HelveticaNeue", size: 13))
            .lineSpacing(5)
    }
}
```

您可以在视图中定义文本的样式，包括文本颜色、字体和行距。您可以通过对视图应用标准视图修改器来定义这些样式。

默认文本编辑器不支持富文本，例如编辑器视图中单个元素的样式。您设置的样式会全局应用于视图中的所有文本。


---
source: https://developer.apple.com/documentation/SwiftUI/TextEditor/init(text:)
crawled: 2025-12-02T17:51:54Z
---

# init(text:)

**Initializer**

Creates a plain text editor.

## Declaration

```swift
init(text: Binding<String>)
```

## Parameters

- **text**: A [Binding](../Binding.zh-Hans.md) to the variable containing the text to edit.

## Discussion

Use a [TextEditor](../TextEditor.zh-Hans.md) instance to create a view in which users can enter and edit long-form text.

In this example, the text editor renders gray text using the 13 point Helvetica Neue font with 5 points of spacing between each line:

```swift
struct TextEditingView: View {
    @State private var fullText: String = "This is some editable text..."

    var body: some View {
        TextEditor(text: $fullText)
            .foregroundColor(Color.gray)
            .font(.custom("HelveticaNeue", size: 13))
            .lineSpacing(5)
    }
}
```

You can define the styling for the text within the view, including the text color, font, and line spacing. You define these styles by applying standard view modifiers to the view.

The default text editor doesn’t support rich text, such as styling of individual elements within the editor’s view. The styles you set apply globally to all text in the view.

