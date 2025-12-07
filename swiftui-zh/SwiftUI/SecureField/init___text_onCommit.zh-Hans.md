--- 来源：https://developer.apple.com/documentation/SwiftUI/SecureField/init(_:text:onCommit:)

抓取时间：2025-11-30T21:36:41Z

---

# init(_:text:onCommit:)

**Initializer**

创建一个实例。

## 声明

```swift
nonisolated init(_ titleKey: LocalizedStringKey, text: Binding<String>, onCommit: @escaping () -> Void)
```

## 参数

- **titleKey**：`self` 的本地化标题键，用于描述其用途。

- **text**：要显示和编辑的文本。

- **onCommit**：当用户在安全字段获得焦点时执行操作（通常是按下回车键）时要执行的操作。


---
source: https://developer.apple.com/documentation/SwiftUI/SecureField/init(_:text:onCommit:)
crawled: 2025-11-30T21:36:41Z
---

# init(_:text:onCommit:)

**Initializer**

Creates an instance.

## Declaration

```swift
nonisolated init(_ titleKey: LocalizedStringKey, text: Binding<String>, onCommit: @escaping () -> Void)
```

## Parameters

- **titleKey**: The key for the localized title of `self`, describing its purpose.
- **text**: The text to display and edit.
- **onCommit**: The action to perform when the user performs an action (usually pressing the Return key) while the secure field has focus.

