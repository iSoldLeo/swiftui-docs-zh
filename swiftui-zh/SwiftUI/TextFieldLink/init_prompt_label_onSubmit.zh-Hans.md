---
来源：https://developer.apple.com/documentation/SwiftUI/TextFieldLink/init(prompt:label:onSubmit:)
抓取时间：2025-12-01T10:34:42Z


# init(prompt:label:onSubmit:)

**Initializer**

创建一个 TextFieldLink，按下时将要求用户输入文本。

## 声明

```swift
nonisolated init(prompt: Text? = nil, @ViewBuilder label: () -> Label, onSubmit: @escaping (String) -> Void)
```

## 参数

- **prompt**：描述请求文本输入原因的文本。
- **label**：描述请求文本输入操作的视图。
- **onSubmit**：当文本输入被接受和驳回时要执行的操作

## 创建文本字段链接

- **init(_:prompt:onSubmit:)**：创建 TextFieldLink，按下后将要求用户输入文本。


---
source: https://developer.apple.com/documentation/SwiftUI/TextFieldLink/init(prompt:label:onSubmit:)
crawled: 2025-12-01T10:34:42Z
---

# init(prompt:label:onSubmit:)

**Initializer**

Creates a TextFieldLink which when pressed will request text input from the user.

## Declaration

```swift
nonisolated init(prompt: Text? = nil, @ViewBuilder label: () -> Label, onSubmit: @escaping (String) -> Void)
```

## Parameters

- **prompt**: Text which describes the reason for requesting text input.
- **label**: A view that describes the action of requesting text input.
- **onSubmit**: An action to perform when text input has been accepted and dismissed

## Creating a text field link

- **init(_:prompt:onSubmit:)**: Creates a TextFieldLink which when pressed will request text input from the user.

