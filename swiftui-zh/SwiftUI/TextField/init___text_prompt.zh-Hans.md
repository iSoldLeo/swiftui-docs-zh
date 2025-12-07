---
来源：https://developer.apple.com/documentation/SwiftUI/TextField/init(_:文本:提示:)
抓取时间：2025-12-02T17:51:40Z
---

# init(_:text:prompt:)

**Initializer**

创建一个文本字段，其文本标签由本地化标题字符串生成。

## 声明

```swift
nonisolated init(_ titleKey: LocalizedStringKey, text: Binding<String>, prompt: Text?)
```

## 参数

- **titleKey**：文本字段本地化标题的键值，描述其用途。
- **text**：要显示和编辑的文本。
- **prompt**：要显示和编辑的文本：代表文本字段提示的`Text`，可指导用户在文本字段中输入什么内容。

## 讨论

使用[onSubmit(of:_:)](../View/onSubmit_of.zh-Hans.md)修饰符可在用户提交该文本字段时调用一个操作。

## 使用字符串创建文本字段

- **init(_:text:)**：用本地化标题字符串生成的文本标签创建文本字段。
- **init(text:prompt:label:)**：`Text`.SY_0005⟧： 创建带有提示的文本字段，提示由本地化标题字符串生成。


---
source: https://developer.apple.com/documentation/SwiftUI/TextField/init(_:text:prompt:)
crawled: 2025-12-02T17:51:40Z
---

# init(_:text:prompt:)

**Initializer**

Creates a text field with a text label generated from a localized title string.

## Declaration

```swift
nonisolated init(_ titleKey: LocalizedStringKey, text: Binding<String>, prompt: Text?)
```

## Parameters

- **titleKey**: The key for the localized title of the text field, describing its purpose.
- **text**: The text to display and edit.
- **prompt**: A `Text` representing the prompt of the text field which provides users with guidance on what to type into the text field.

## Discussion

Use the [onSubmit(of:_:)](../View/onSubmit_of.zh-Hans.md) modifier to invoke an action whenever the user submits this text field.

## Creating a text field with a string

- **init(_:text:)**: Creates a text field with a text label generated from a localized title string.
- **init(text:prompt:label:)**: Creates a text field with a prompt generated from a `Text`.

