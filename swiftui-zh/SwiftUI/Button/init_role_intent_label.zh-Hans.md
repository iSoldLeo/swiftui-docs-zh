--- 来源：https://developer.apple.com/documentation/SwiftUI/Button/init(role:intent:label:)

抓取时间：2025-12-01T02:39:00Z

---

# init(role:intent:label:)

**Initializer**

创建一个具有指定角色的按钮，该按钮执行 `AppIntent` 操作。

## 声明

```swift
nonisolated init(role: ButtonRole?, intent: some AppIntent, @ViewBuilder label: () -> Label)
```

## 参数

- **role**：一个可选的语义角色，用于描述按钮。值为 `nil` 表示按钮未分配角色。

- **intent**：要执行的 `AppIntent` 操作。

- **label**：描述按钮 `action` 用途的视图。

## 创建用于执行应用意图的按钮

- **init(_:intent:)**：创建一个执行 `AppIntent` 的按钮，并根据本地化字符串键生成其标签。

- **init(intent:label:)**：创建一个执行 `AppIntent` 的按钮。

- **init(_:role:intent:)**：创建一个具有指定角色的按钮，该按钮执行 `AppIntent` 并根据字符串生成其标签。

- **init(_:image:role:intent:)**：创建一个具有指定角色的按钮，该按钮根据字符串和图像资源生成其标签。

- **init(_:systemImage:role:intent:)**：创建一个具有指定角色的按钮，该按钮的标签由字符串和系统图像生成。


---
source: https://developer.apple.com/documentation/SwiftUI/Button/init(role:intent:label:)
crawled: 2025-12-01T02:39:00Z
---

# init(role:intent:label:)

**Initializer**

Creates a button with a specified role that performs an `AppIntent`.

## Declaration

```swift
nonisolated init(role: ButtonRole?, intent: some AppIntent, @ViewBuilder label: () -> Label)
```

## Parameters

- **role**: An optional semantic role describing the button. A value of `nil` means that the button doesn’t have an assigned role.
- **intent**: The `AppIntent` to execute.
- **label**: A view that describes the purpose of the button’s `action`.

## Creating a button to perform an App Intent

- **init(_:intent:)**: Creates a button that performs an `AppIntent` and generates its label from a localized string key.
- **init(intent:label:)**: Creates a button that performs an `AppIntent`.
- **init(_:role:intent:)**: Creates a button with a specified role that performs an `AppIntent` and generates its label from a string.
- **init(_:image:role:intent:)**: Creates a button with a specified role that generates its label from a string and an image resource.
- **init(_:systemImage:role:intent:)**: Creates a button with a specified role that generates its label from a string and a system image.

