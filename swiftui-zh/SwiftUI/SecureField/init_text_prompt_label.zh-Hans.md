--- 来源：https://developer.apple.com/documentation/SwiftUI/SecureField/init(text:prompt:label:)

抓取时间：2025-12-02T17:51:52Z

---

# init(text:prompt:label:)

**Initializer**

创建一个安全字段，其提示信息由 `Text` 生成。

## 声明

```swift
nonisolated init(text: Binding<String>, prompt: Text? = nil, @ViewBuilder label: () -> Label)
```

## 参数

- **text**：字段显示和编辑的文本绑定。

- **prompt**：表示安全字段提示信息的 [Text](../Text.zh-Hans.md) 视图。提示信息指导用户在安全字段中输入什么内容。

- **label**：描述安全字段用途的视图。

## 讨论

使用 [onSubmit(of:_:)](../View/onSubmit_of.zh-Hans.md) 修饰符，可在用户提交此安全字段时触发操作，例如，按下回车键。

## 创建安全文本字段

- **init(_:text:)**：创建一个安全字段，其提示信息由 `Text` 生成。

- **init(_:text:prompt:)**：创建一个安全字段，其提示信息由 `Text` 生成。


---
source: https://developer.apple.com/documentation/SwiftUI/SecureField/init(text:prompt:label:)
crawled: 2025-12-02T17:51:52Z
---

# init(text:prompt:label:)

**Initializer**

Creates a secure field with a prompt generated from a `Text`.

## Declaration

```swift
nonisolated init(text: Binding<String>, prompt: Text? = nil, @ViewBuilder label: () -> Label)
```

## Parameters

- **text**: A binding to the text that the field displays and edits.
- **prompt**: A [Text](../Text.zh-Hans.md) view that represents the secure field’s prompt. The prompt provides guidance on what people should type into the secure field.
- **label**: A view that describes the purpose of the secure field.

## Discussion

Use the [onSubmit(of:_:)](../View/onSubmit_of.zh-Hans.md) modifier to invoke an action whenever someone submits this secure field — for example, by pressing the Return key.

## Creating a secure text field

- **init(_:text:)**: Creates a secure field with a prompt generated from a `Text`.
- **init(_:text:prompt:)**: Creates a secure field with a prompt generated from a `Text`.

