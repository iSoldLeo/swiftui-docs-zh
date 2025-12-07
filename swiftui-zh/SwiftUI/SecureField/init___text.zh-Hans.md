--- 来源：https://developer.apple.com/documentation/SwiftUI/SecureField/init(_:text:)

抓取时间：2025-12-02T17:51:51Z

---

# init(_:text:)

**Initializer**

创建一个安全字段，其提示信息由 `Text` 生成。

## 声明

```swift
nonisolated init(_ titleKey: LocalizedStringKey, text: Binding<String>)
```

## 参数

- **titleKey**：字段本地化标题的键。标题描述字段的用途。

- **text**：字段显示和编辑的文本的绑定。

## 讨论

使用 [onSubmit(of:_:)](../View/onSubmit_of.zh-Hans.md) 修饰符，可在用户提交此安全字段时触发操作——例如，按下回车键。

## 创建安全文本字段

- **init(_:text:prompt:)**：创建一个安全字段，其提示信息由 `Text` 生成。

- **init(text:prompt:label:)**：创建一个安全字段，其提示信息由 `Text` 生成。


---
source: https://developer.apple.com/documentation/SwiftUI/SecureField/init(_:text:)
crawled: 2025-12-02T17:51:51Z
---

# init(_:text:)

**Initializer**

Creates a secure field with a prompt generated from a `Text`.

## Declaration

```swift
nonisolated init(_ titleKey: LocalizedStringKey, text: Binding<String>)
```

## Parameters

- **titleKey**: The key for the field’s localized title. The title describes the purpose of the field.
- **text**: A binding to the text that the field displays and edits.

## Discussion

Use the [onSubmit(of:_:)](../View/onSubmit_of.zh-Hans.md) modifier to invoke an action whenever someone submits this secure field — for example, by pressing the Return key.

## Creating a secure text field

- **init(_:text:prompt:)**: Creates a secure field with a prompt generated from a `Text`.
- **init(text:prompt:label:)**: Creates a secure field with a prompt generated from a `Text`.

