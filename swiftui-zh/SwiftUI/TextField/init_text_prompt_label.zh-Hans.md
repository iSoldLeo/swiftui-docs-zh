---
来源：https://developer.apple.com/documentation/SwiftUI/TextField/init(文本:提示:标签:)
抓取时间：2025-12-02T17:51:41Z
---

# init(text:prompt:label:)

**Initializer**

创建一个文本字段，其提示信息由 `Text` 生成。

## 声明

```swift
nonisolated init(text: Binding<String>, prompt: Text? = nil, @ViewBuilder label: () -> Label)
```

## 参数

- **text**：要显示和编辑的文本。
- **prompt**：代表文本字段提示的`Text`，可指导用户在文本字段中输入什么内容。
- **label**：描述文本字段用途的视图。

## 讨论

使用[onSubmit(of:_:)](../View/onSubmit_of.zh-Hans.md)修饰符可在用户提交此文本字段时调用一个操作。

## 使用字符串创建文本字段

- **init(_:text:)**：用本地化标题字符串生成的文本标签创建文本字段。
- **init(_:text:prompt:)**：创建文本字段，文本标签由本地化标题字符串生成。


---
source: https://developer.apple.com/documentation/SwiftUI/TextField/init(text:prompt:label:)
crawled: 2025-12-02T17:51:41Z
---

# init(text:prompt:label:)

**Initializer**

Creates a text field with a prompt generated from a `Text`.

## Declaration

```swift
nonisolated init(text: Binding<String>, prompt: Text? = nil, @ViewBuilder label: () -> Label)
```

## Parameters

- **text**: The text to display and edit.
- **prompt**: A `Text` representing the prompt of the text field which provides users with guidance on what to type into the text field.
- **label**: A view that describes the purpose of the text field.

## Discussion

Use the [onSubmit(of:_:)](../View/onSubmit_of.zh-Hans.md) modifier to invoke an action whenever the user submits this text field.

## Creating a text field with a string

- **init(_:text:)**: Creates a text field with a text label generated from a localized title string.
- **init(_:text:prompt:)**: Creates a text field with a text label generated from a localized title string.

