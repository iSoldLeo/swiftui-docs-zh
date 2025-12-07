--- 来源：https://developer.apple.com/documentation/SwiftUI/Button/init(_:systemImage:role:intent:)

抓取时间：2025-12-02T21:48:10Z

---

# init(_:systemImage:role:intent:)

**Initializer**

创建一个具有指定角色的按钮，该按钮的标签由字符串和系统图像生成。

## 声明

```swift
nonisolated init(_ title: some StringProtocol, systemImage: String, role: ButtonRole? = nil, intent: some AppIntent)
```

## 参数

- **title**：描述按钮用途的字符串。

- **systemImage**：要查找的图像资源的名称。

- **role**：描述按钮的可选语义角色。 `nil` 的值表示该按钮未分配角色。

- **intent**：要执行的 `AppIntent`。

## 讨论

此初始化程序会代表您创建一个 [Label](../Label.zh-Hans.md) 视图，并且其标题的处理方式与 [doc://com.apple.SwiftUI/documentation/SwiftUI/Text/init(_:)-9d1g4] 类似。有关字符串本地化的更多信息，请参阅 [Text](../Text.zh-Hans.md)。

## 创建用于执行 App Intent 的按钮

- **init(_:intent:)**：创建一个执行 `AppIntent` 的按钮，并根据本地化的字符串键生成其标签。

- **init(intent:label:)**：创建一个执行 `AppIntent` 的按钮。

- **init(_:role:intent:)**：创建一个具有指定角色的按钮，执行 `AppIntent` 操作，并根据字符串生成其标签。

- **init(role:intent:label:)**：创建一个具有指定角色的按钮，执行 `AppIntent` 操作。

- **init(_:image:role:intent:)**：创建一个具有指定角色的按钮，根据字符串和图像资源生成其标签。


---
source: https://developer.apple.com/documentation/SwiftUI/Button/init(_:systemImage:role:intent:)
crawled: 2025-12-02T21:48:10Z
---

# init(_:systemImage:role:intent:)

**Initializer**

Creates a button with a specified role that generates its label from a string and a system image.

## Declaration

```swift
nonisolated init(_ title: some StringProtocol, systemImage: String, role: ButtonRole? = nil, intent: some AppIntent)
```

## Parameters

- **title**: A string that describes the purpose of the button’s `intent`.
- **systemImage**: The name of the image resource to lookup.
- **role**: An optional semantic role describing the button. A value of `nil` means that the button doesn’t have an assigned role.
- **intent**: The `AppIntent` to execute.

## Discussion

This initializer creates a [Label](../Label.zh-Hans.md) view on your behalf, and treats the title similar to [doc://com.apple.SwiftUI/documentation/SwiftUI/Text/init(_:)-9d1g4]. See [Text](../Text.zh-Hans.md) for more information about localizing strings.

## Creating a button to perform an App Intent

- **init(_:intent:)**: Creates a button that performs an `AppIntent` and generates its label from a localized string key.
- **init(intent:label:)**: Creates a button that performs an `AppIntent`.
- **init(_:role:intent:)**: Creates a button with a specified role that performs an `AppIntent` and generates its label from a string.
- **init(role:intent:label:)**: Creates a button with a specified role that performs an `AppIntent`.
- **init(_:image:role:intent:)**: Creates a button with a specified role that generates its label from a string and an image resource.

