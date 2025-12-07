--- 来源：https://developer.apple.com/documentation/SwiftUI/SecureField
抓取时间：2025-12-02T16:03:24Z

---

# SecureField

**Structure**

一个用于安全输入私密文本的控件。

## 声明

```swift
struct SecureField<Label> where Label : View
```

## 概述

如果您想要实现 [TextField](TextField.zh-Hans.md) 的行为，但又想隐藏字段文本，请使用安全字段。通常，您会使用此功能来输入密码和其他敏感信息，如下方屏幕截图中的第二个字段所示：

该字段：

- 用户输入的每个字符都会显示一个点。

- 当用户在 iOS 中截屏时，这些点会被隐藏。

- 防止任何人剪切或复制字段内容。

- 当启用大写锁定时，会显示指示器。

### 绑定到字符串

安全字段绑定到一个字符串值，并在每次按键或其他编辑操作时更新该字符串，以便您可以随时从代码中的其他位置读取其值。以下代码展示了如何创建上述接口，并将安全字段绑定到字符串 `password`：

```swift
@State private var username: String = ""
@State private var password: String = ""

var body: some View {
    VStack {
        TextField("Username", text: $username)
            .autocorrectionDisabled(true)
            #if !os(macOS)
            .textInputAutocapitalization(.never)
            #endif

        SecureField("Password", text: $password)
            .onSubmit {
                handleLogin(username: username, password: password)
            }
    }
    .textFieldStyle(.roundedBorder)
}
```

上述示例中的字段有一个 [onSubmit(of:_:)](View/onSubmit_of.zh-Hans.md) 修饰符，当用户在安全字段获得焦点时按下回车键，该修饰符会将字符串 `username` 和 `password` 发送到自定义方法 `handleLogin(username:password:)`。您也可以提供其他机制（例如按钮）来实现相同的功能。

### 使用提示引导用户

除了您提供的字符串或视图作为标签外，您还可以提供一个 [Text](Text.zh-Hans.md) 视图提示，以帮助引导使用该字段的用户，如下例 [Form](Form.zh-Hans.md) 所示：

```swift
Form {
    TextField(text: $username, prompt: Text("Required")) {
        Text("Username")
    }
    .autocorrectionDisabled(true)
    #if !os(macOS)
    .textInputAutocapitalization(.never)
    #endif

    SecureField(text: $password, prompt: Text("Required")) {
        Text("Password")
    }
}
```

系统会根据上下文以不同的方式使用标签和提示。例如，macOS 中的表单会将标签放置在字段的前缘，并将提示用作字段内的占位符文本。 iOS 中的同一表单也使用提示作为占位符文本，但不会显示标签：

如果从上一个示例中移除提示，则在 macOS 中，字段会保留位于前沿的标签并省略占位符文本，但在 iOS 中，标签会显示为占位符：

## 创建安全文本字段

- **init(_:text:)**：创建一个安全字段，其提示由 `Text` 生成。

- **init(_:text:prompt:)**：创建一个安全字段，其提示由 `Text` 生成。

- **init(text:prompt:label:)**：创建一个安全字段，其提示由 `Text` 生成。

## 已弃用的初始化器

- **init(_:text:onCommit:)**：创建一个实例。

## 获取文本输入

- **构建丰富的 SwiftUI 文本体验**：使用 SwiftUI 文本编辑器视图和属性字符串构建格式化文本编辑器。

- **TextField**：显示可编辑文本界面的控件。

- **textFieldStyle(_:)**：设置此视图中文本字段的样式。

- **TextEditor**：可以显示和编辑长文本的视图。

## 符合以下规范

- View


---
source: https://developer.apple.com/documentation/SwiftUI/SecureField
crawled: 2025-12-02T16:03:24Z
---

# SecureField

**Structure**

A control into which people securely enter private text.

## Declaration

```swift
struct SecureField<Label> where Label : View
```

## Overview

Use a secure field when you want the behavior of a [TextField](TextField.zh-Hans.md), but you want to hide the field’s text. Typically, you use this for entering passwords and other sensitive information, as the second field in the following screenshot demonstrates:



The field:

- Displays one dot for each character someone types.
- Hides the dots when someone takes a screenshot in iOS.
- Prevents anyone from cutting or copying the field’s contents.
- Displays an indicator when Caps Lock is enabled.

### Bind to a string

A secure field binds to a string value and updates the string on every keystroke or other edit, so you can read its value at any time from elsewhere in your code. The following code shows how to create the above interface, with the secure field bound to a `password` string:

```swift
@State private var username: String = ""
@State private var password: String = ""

var body: some View {
    VStack {
        TextField("Username", text: $username)
            .autocorrectionDisabled(true)
            #if !os(macOS)
            .textInputAutocapitalization(.never)
            #endif

        SecureField("Password", text: $password)
            .onSubmit {
                handleLogin(username: username, password: password)
            }
    }
    .textFieldStyle(.roundedBorder)
}
```

The field in the above example has an [onSubmit(of:_:)](View/onSubmit_of.zh-Hans.md) modifier that sends the `username` and `password` strings to a custom `handleLogin(username:password:)` method if someone presses the Return key while the secure field has focus. You can alternatively provide another mechanism — like a button — to do the same thing.

### Guide people with a prompt

In addition to the string or view that you provide as a label, you can also provide a [Text](Text.zh-Hans.md) view prompt to help guide someone who uses the field, as the following [Form](Form.zh-Hans.md) does:

```swift
Form {
    TextField(text: $username, prompt: Text("Required")) {
        Text("Username")
    }
    .autocorrectionDisabled(true)
    #if !os(macOS)
    .textInputAutocapitalization(.never)
    #endif

    SecureField(text: $password, prompt: Text("Required")) {
        Text("Password")
    }
}
```

The system uses the label and prompt in different ways depending on the context. For example, a form in macOS places the label against the leading edge of the field and uses the prompt as placeholder text inside the field. The same form in iOS also uses the prompt as placeholder text, but doesn’t display the label:



If you remove the prompt from the previous example, the field keeps the label on the leading edge and omits the placeholder text in macOS, but displays the label as a placeholder in iOS:



## Creating a secure text field

- **init(_:text:)**: Creates a secure field with a prompt generated from a `Text`.
- **init(_:text:prompt:)**: Creates a secure field with a prompt generated from a `Text`.
- **init(text:prompt:label:)**: Creates a secure field with a prompt generated from a `Text`.

## Deprecated initializers

- **init(_:text:onCommit:)**: Creates an instance.

## Getting text input

- **Building rich SwiftUI text experiences**: Build an editor for formatted text using SwiftUI text editor views and attributed strings.
- **TextField**: A control that displays an editable text interface.
- **textFieldStyle(_:)**: Sets the style for text fields within this view.
- **TextEditor**: A view that can display and edit long-form text.

## Conforms To

- View

