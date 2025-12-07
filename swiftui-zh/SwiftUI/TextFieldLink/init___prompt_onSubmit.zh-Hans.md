---
来源：https://developer.apple.com/documentation/SwiftUI/TextFieldLink/init(_:prompt:onSubmit:)
抓取时间：2025-12-01T10:34:41Z


# init(_:prompt:onSubmit:)

**Initializer**

创建一个 TextFieldLink，按下时将要求用户输入文本。

## 声明

```swift
nonisolated init(_ titleKey: LocalizedStringKey, prompt: Text? = nil, onSubmit: @escaping (String) -> Void)
```

## 参数

- **titleKey**：用于 TextFieldLink 本地化标题的键，描述请求文本输入的目的。
- **prompt**：描述请求文本输入的原因的文本。
- **onSubmit**：文本输入被接受和驳回时要执行的操作

## 创建文本字段链接

- **init(prompt:label:onSubmit:)**：创建 TextFieldLink，按下后将要求用户输入文本。


---
source: https://developer.apple.com/documentation/SwiftUI/TextFieldLink/init(_:prompt:onSubmit:)
crawled: 2025-12-01T10:34:41Z
---

# init(_:prompt:onSubmit:)

**Initializer**

Creates a TextFieldLink which when pressed will request text input from the user.

## Declaration

```swift
nonisolated init(_ titleKey: LocalizedStringKey, prompt: Text? = nil, onSubmit: @escaping (String) -> Void)
```

## Parameters

- **titleKey**: A key for the TextFieldLink’s localized title, that describes the purpose of requesting text input.
- **prompt**: Text which describes the reason for requesting text input.
- **onSubmit**: An action to perform when text input has been accepted and dismissed

## Creating a text field link

- **init(prompt:label:onSubmit:)**: Creates a TextFieldLink which when pressed will request text input from the user.

