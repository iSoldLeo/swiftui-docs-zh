--- 来源：https://developer.apple.com/documentation/SwiftUI/TextEditor

抓取时间：2025-12-02T16:03:25Z

---

# 文本编辑器

**Structure**

一个可以显示和编辑长文本的视图。

## 声明

```swift
struct TextEditor
```

## 概述

文本编辑器视图允许您在应用程序的用户界面中显示和编辑多行可滚动文本。默认情况下，文本编辑器视图使用从环境继承的特征（例如 [font(_:)](View/font.zh-Hans.md)、[foregroundColor(_:)](View/foregroundColor.zh-Hans.md) 和 [multilineTextAlignment(_:)](View/multilineTextAlignment.zh-Hans.md)）来设置文本样式。

您可以通过在视图主体中添加一个 `TextEditor` 实例来创建文本编辑器，并通过将 [Binding](Binding.zh-Hans.md) 传递给应用程序中的字符串变量来初始化它：

```swift
struct TextEditingView: View {
    @State private var fullText: String = "This is some editable text..."

    var body: some View {
        TextEditor(text: $fullText)
    }
}
```

要设置文本样式，请使用标准视图修饰符来配置系统字体、设置自定义字体或更改视图文本的颜色。

在本例中，视图使用自定义字体以灰色渲染编辑器文本：

```swift
struct TextEditingView: View {
    @State private var fullText: String = "This is some editable text..."

    var body: some View {
        TextEditor(text: $fullText)
            .foregroundColor(Color.gray)
            .font(.custom("HelveticaNeue", size: 13))
    }
}
```

如果您想要更改文本的间距或字体缩放，可以使用 [lineLimit(_:)](View/lineLimit.zh-Hans.md)、[lineSpacing(_:)](View/lineSpacing.zh-Hans.md) 和 [minimumScaleFactor(_:)](View/minimumScaleFactor.zh-Hans.md) 等修饰符来配置视图如何根据空间限制显示文本。例如，这里的 [lineSpacing(_:)](View/lineSpacing.zh-Hans.md) 修饰符将行间距设置为 5 磅：

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

## 创建文本编辑器

- **init(text:)**：创建一个纯文本编辑器。

## 初始化器

- **init(text:selection:)**：创建一个带样式的文本编辑器。

## 获取文本输入

- **构建丰富的 SwiftUI 文本体验**：使用 SwiftUI 文本编辑器视图和属性字符串构建格式化文本编辑器。

- **TextField**：一个显示可编辑文本界面的控件。

- **textFieldStyle(_:)**：设置此视图中文本字段的样式。

- **SecureField**：一个供用户安全输入私密文本的控件。

## 符合

- 查看


---
source: https://developer.apple.com/documentation/SwiftUI/TextEditor
crawled: 2025-12-02T16:03:25Z
---

# TextEditor

**Structure**

A view that can display and edit long-form text.

## Declaration

```swift
struct TextEditor
```

## Overview

A text editor view allows you to display and edit multiline, scrollable text in your app’s user interface. By default, the text editor view styles the text using characteristics inherited from the environment, like [font(_:)](View/font.zh-Hans.md), [foregroundColor(_:)](View/foregroundColor.zh-Hans.md), and [multilineTextAlignment(_:)](View/multilineTextAlignment.zh-Hans.md).

You create a text editor by adding a `TextEditor` instance to the body of your view, and initialize it by passing in a [Binding](Binding.zh-Hans.md) to a string variable in your app:

```swift
struct TextEditingView: View {
    @State private var fullText: String = "This is some editable text..."

    var body: some View {
        TextEditor(text: $fullText)
    }
}
```

To style the text, use the standard view modifiers to configure a system font, set a custom font, or change the color of the view’s text.

In this example, the view renders the editor’s text in gray with a custom font:

```swift
struct TextEditingView: View {
    @State private var fullText: String = "This is some editable text..."

    var body: some View {
        TextEditor(text: $fullText)
            .foregroundColor(Color.gray)
            .font(.custom("HelveticaNeue", size: 13))
    }
}
```

If you want to change the spacing or font scaling aspects of the text, you can use modifiers like [lineLimit(_:)](View/lineLimit.zh-Hans.md), [lineSpacing(_:)](View/lineSpacing.zh-Hans.md), and [minimumScaleFactor(_:)](View/minimumScaleFactor.zh-Hans.md) to configure how the view displays text depending on the space constraints. For example, here the [lineSpacing(_:)](View/lineSpacing.zh-Hans.md) modifier sets the spacing between lines to 5 points:

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

## Creating a text editor

- **init(text:)**: Creates a plain text editor.

## Initializers

- **init(text:selection:)**: Creates a styled text editor.

## Getting text input

- **Building rich SwiftUI text experiences**: Build an editor for formatted text using SwiftUI text editor views and attributed strings.
- **TextField**: A control that displays an editable text interface.
- **textFieldStyle(_:)**: Sets the style for text fields within this view.
- **SecureField**: A control into which people securely enter private text.

## Conforms To

- View

