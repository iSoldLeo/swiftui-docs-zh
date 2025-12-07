--- 来源：https://developer.apple.com/documentation/SwiftUI/TextField
抓取时间：2025-12-02T16:03:23Z

---

# TextField

**Structure**

一个显示可编辑文本界面的控件。

## 声明

```swift
struct TextField<Label> where Label : View
```

## 概述

您可以创建一个带有标签和值绑定的文本字段。如果该值为字符串，则当用户在字段中输入或编辑文本时，文本字段会持续更新该值。对于非字符串类型，它会在用户提交编辑操作（例如按下回车键）时更新该值。

以下示例显示了一个用于接收用户名的文本字段，以及其下方的 [Text](Text.zh-Hans.md) 视图，该视图会显示 `username` 的持续更新值。当用户开始和结束编辑时，[Text](Text.zh-Hans.md) 视图会改变颜色。当用户将完成的条目提交到文本字段时，[onSubmit(of:_:)](View/onSubmit_of.zh-Hans.md) 修饰符会调用内部方法 `validate(name:)`。

```swift
@State private var username: String = ""
@FocusState private var emailFieldIsFocused: Bool = false

var body: some View {
    TextField(
        "User name (email address)",
        text: $username
    )
    .focused($emailFieldIsFocused)
    .onSubmit {
        validate(name: username)
    }
    .textInputAutocapitalization(.never)
    .disableAutocorrection(true)
    .border(.secondary)

    Text(username)
        .foregroundColor(emailFieldIsFocused ? .red : .blue)
}
```

绑定值不必是字符串。通过使用 [doc://com.apple.documentation/documentation/Foundation/FormatStyle]，您可以将文本字段绑定到非字符串类型，并使用格式样式将输入的文本转换为绑定类型的实例。以下示例使用 [doc://com.apple.documentation/documentation/Foundation/PersonNameComponents/FormatStyle] 将文本字段中输入的名称转换为 [doc://com.apple.documentation/documentation/Foundation/PersonNameComponents] 实例。文本字段下方的 [Text](Text.zh-Hans.md) 视图显示此实例的调试描述字符串。

```swift
@State private var nameComponents = PersonNameComponents()

var body: some View {
    TextField(
        "Proper name",
        value: $nameComponents,
        format: .name(style: .medium)
    )
    .onSubmit {
        validate(components: nameComponents)
    }
    .disableAutocorrection(true)
    .border(.secondary)
    Text(nameComponents.debugDescription)
}
```

### 文本字段提示

您可以为文本字段设置明确的提示，引导用户输入正确的文本。每个文本字段样式决定了文本字段何时何地使用提示和标签。例如，macOS 上的表单始终将标签放置在字段的前端，并在可用时使用提示作为字段内的占位符文本。在 iOS 上，文本字段会根据初始化程序是否提供了提示，使用提示或标签作为占位符文本。

以下示例展示了一个包含两个文本字段的 [Form](Form.zh-Hans.md)，每个文本字段都提供了一个提示来指示该字段为必填项，以及一个用于提供标签的视图构建器：

```swift
Form {
    TextField(text: $username, prompt: Text("Required")) {
        Text("Username")
    }
    SecureField(text: $password, prompt: Text("Required")) {
        Text("Password")
    }
}
```

### 文本字段样式

SwiftUI 提供了一个默认的文本字段样式，该样式反映了适合平台的视觉效果和行为。默认样式还会考虑当前上下文，例如文本字段是否位于以特殊样式显示文本字段的容器中。此外，您可以使用 [textFieldStyle(_:)](View/textFieldStyle.zh-Hans.md) 修饰符自定义文本字段的外观和交互，并传入 [TextFieldStyle](TextFieldStyle.zh-Hans.md) 的实例。以下示例将 [roundedBorder](TextFieldStyle/roundedBorder.zh-Hans.md) 样式应用于 [VStack](VStack.zh-Hans.md) 内的两个文本字段。

```swift
@State private var givenName: String = ""
@State private var familyName: String = ""

var body: some View {
    VStack {
        TextField(
            "Given Name",
            text: $givenName
        )
        .disableAutocorrection(true)
        TextField(
            "Family Name",
            text: $familyName
        )
        .disableAutocorrection(true)
    }
    .textFieldStyle(.roundedBorder)
}
```

## 创建带有字符串的文本字段

- **init(_:text:)**：创建一个文本字段，其文本标签由本地化标题字符串生成。

- **init(_:text:prompt:)**：创建一个文本字段，其文本标签由本地化标题字符串生成。

- **init(text:prompt:label:)**：创建一个文本字段，其提示信息由 `Text` 生成。

## 创建可滚动文本字段

- **init(_:text:axis:)**：创建一个文本字段，其具有首选坐标轴，并且其文本标签由本地化标题字符串生成。

- **init(_:text:prompt:axis:)**：创建一个文本字段，其具有首选坐标轴，并且其文本标签由本地化标题字符串生成。

- **init(text:prompt:axis:label:)**：创建一个文本字段，其具有首选坐标轴，并且其提示信息由 `Text` 生成。

## 创建带值的文本字段

- **init(_:value:format:prompt:)**：创建一个文本字段，该字段将格式样式应用于绑定值，并且其标签由本地化标题字符串生成。

- **init(value:format:prompt:label:)**：创建一个文本字段，该字段将格式样式应用于绑定值，标签由视图构建器生成。

- **init(_:value:formatter:)**：创建一个绑定任意类型 `V` 的实例。

- **init(_:value:formatter:prompt:)**：创建一个文本字段，该字段将格式化程序应用于绑定值，标签由标题字符串生成。

- **init(value:formatter:prompt:label:)**：创建一个文本字段，该字段将格式化程序应用于绑定的可选值，标签由视图构建器生成。

## 已弃用的初始化程序

- **已弃用的初始化程序**：查看已弃用的文本字段初始化程序。

## 初始化器

- **init(_:text:selection:prompt:axis:)**：创建一个文本字段，绑定到当前选中项，并使用本地化标题字符串生成文本标签。

- **init(text:selection:prompt:axis:label:)**：创建一个文本字段，绑定到当前选中项，并使用 `Text` 生成提示。

## 获取文本输入

- **构建丰富的 SwiftUI 文本体验**：使用 SwiftUI 文本编辑器视图和属性字符串构建格式化文本编辑器。

- **textFieldStyle(_:)**：设置此视图中文本字段的样式。

- **SecureField**：一个用于安全输入私密文本的控件。

- **TextEditor**：一个可以显示和编辑长文本的视图。

## 符合以下规范

- View


---
source: https://developer.apple.com/documentation/SwiftUI/TextField
crawled: 2025-12-02T16:03:23Z
---

# TextField

**Structure**

A control that displays an editable text interface.

## Declaration

```swift
struct TextField<Label> where Label : View
```

## Overview

You create a text field with a label and a binding to a value. If the value is a string, the text field updates this value continuously as the user types or otherwise edits the text in the field. For non-string types, it updates the value when the user commits their edits, such as by pressing the Return key.

The following example shows a text field to accept a username, and a [Text](Text.zh-Hans.md) view below it that shadows the continuously updated value of `username`. The [Text](Text.zh-Hans.md) view changes color as the user begins and ends editing. When the user submits their completed entry to the text field, the [onSubmit(of:_:)](View/onSubmit_of.zh-Hans.md) modifier calls an internal `validate(name:)` method.

```swift
@State private var username: String = ""
@FocusState private var emailFieldIsFocused: Bool = false

var body: some View {
    TextField(
        "User name (email address)",
        text: $username
    )
    .focused($emailFieldIsFocused)
    .onSubmit {
        validate(name: username)
    }
    .textInputAutocapitalization(.never)
    .disableAutocorrection(true)
    .border(.secondary)

    Text(username)
        .foregroundColor(emailFieldIsFocused ? .red : .blue)
}
```



The bound value doesn’t have to be a string. By using a [doc://com.apple.documentation/documentation/Foundation/FormatStyle], you can bind the text field to a nonstring type, using the format style to convert the typed text into an instance of the bound type. The following example uses a [doc://com.apple.documentation/documentation/Foundation/PersonNameComponents/FormatStyle] to convert the name typed in the text field to a [doc://com.apple.documentation/documentation/Foundation/PersonNameComponents] instance. A [Text](Text.zh-Hans.md) view below the text field shows the debug description string of this instance.

```swift
@State private var nameComponents = PersonNameComponents()

var body: some View {
    TextField(
        "Proper name",
        value: $nameComponents,
        format: .name(style: .medium)
    )
    .onSubmit {
        validate(components: nameComponents)
    }
    .disableAutocorrection(true)
    .border(.secondary)
    Text(nameComponents.debugDescription)
}
```



### Text field prompts

You can set an explicit prompt on the text field to guide users on what text they should provide. Each text field style determines where and when the text field uses a prompt and label. For example, a form on macOS always places the label at the leading edge of the field and uses a prompt, when available, as placeholder text within the field itself. In the same context on iOS, the text field uses either the prompt or label as placeholder text, depending on whether the initializer provided a prompt.

The following example shows a [Form](Form.zh-Hans.md) with two text fields, each of which provides a prompt to indicate that the field is required, and a view builder to provide a label:

```swift
Form {
    TextField(text: $username, prompt: Text("Required")) {
        Text("Username")
    }
    SecureField(text: $password, prompt: Text("Required")) {
        Text("Password")
    }
}
```





### Styling text fields

SwiftUI provides a default text field style that reflects an appearance and behavior appropriate to the platform. The default style also takes the current context into consideration, like whether the text field is in a container that presents text fields with a special style. Beyond this, you can customize the appearance and interaction of text fields using the [textFieldStyle(_:)](View/textFieldStyle.zh-Hans.md) modifier, passing in an instance of [TextFieldStyle](TextFieldStyle.zh-Hans.md). The following example applies the [roundedBorder](TextFieldStyle/roundedBorder.zh-Hans.md) style to both text fields within a [VStack](VStack.zh-Hans.md).

```swift
@State private var givenName: String = ""
@State private var familyName: String = ""

var body: some View {
    VStack {
        TextField(
            "Given Name",
            text: $givenName
        )
        .disableAutocorrection(true)
        TextField(
            "Family Name",
            text: $familyName
        )
        .disableAutocorrection(true)
    }
    .textFieldStyle(.roundedBorder)
}
```



## Creating a text field with a string

- **init(_:text:)**: Creates a text field with a text label generated from a localized title string.
- **init(_:text:prompt:)**: Creates a text field with a text label generated from a localized title string.
- **init(text:prompt:label:)**: Creates a text field with a prompt generated from a `Text`.

## Creating a scrollable text field

- **init(_:text:axis:)**: Creates a text field with a preferred axis and a text label generated from a localized title string.
- **init(_:text:prompt:axis:)**: Creates a text field with a preferred axis and a text label generated from a localized title string.
- **init(text:prompt:axis:label:)**: Creates a text field with a preferred axis and a prompt generated from a `Text`.

## Creating a text field with a value

- **init(_:value:format:prompt:)**: Creates a text field that applies a format style to a bound value, with a label generated from a localized title string.
- **init(value:format:prompt:label:)**: Creates a text field that applies a format style to a bound value, with a label generated from a view builder.
- **init(_:value:formatter:)**: Create an instance which binds over an arbitrary type, `V`.
- **init(_:value:formatter:prompt:)**: Creates a text field that applies a formatter to a bound value, with a label generated from a title string.
- **init(value:formatter:prompt:label:)**: Creates a text field that applies a formatter to a bound optional value, with a label generated from a view builder.

## Deprecated initializers

- **Deprecated initializers**: Review deprecated text field initializers.

## Initializers

- **init(_:text:selection:prompt:axis:)**: Creates a text field with a binding to the current selection and a text label generated from a localized title string.
- **init(text:selection:prompt:axis:label:)**: Creates a text field with a binding to the current selection and a prompt generated from a `Text`.

## Getting text input

- **Building rich SwiftUI text experiences**: Build an editor for formatted text using SwiftUI text editor views and attributed strings.
- **textFieldStyle(_:)**: Sets the style for text fields within this view.
- **SecureField**: A control into which people securely enter private text.
- **TextEditor**: A view that can display and edit long-form text.

## Conforms To

- View

