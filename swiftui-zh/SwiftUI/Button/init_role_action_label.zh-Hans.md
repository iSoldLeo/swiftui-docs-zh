--- 来源：https://developer.apple.com/documentation/SwiftUI/Button/init(role:action:label:)

抓取时间：2025-12-01T02:38:54Z

---

# init(role:action:label:)

**Initializer**

创建一个具有指定角色的按钮，该按钮会显示自定义标签。

## 声明

```swift
@preconcurrency nonisolated init(role: ButtonRole?, action: @escaping @MainActor () -> Void, @ViewBuilder label: () -> Label)
```

## 参数

- **role**：一个可选的语义角色，用于描述按钮。值为 `nil` 表示按钮未分配角色。

- **action**：用户与按钮交互时要执行的操作。

- **label**：描述按钮 `action` 用途的视图。

## 创建具有角色的按钮

- **init(_:role:action:)**：创建一个具有指定角色的按钮，该按钮的标签由本地化字符串键生成。

- **init(_:image:role:action:)**：创建一个具有指定角色的按钮，该按钮的标签由本地化字符串键和图像资源生成。

- **init(_:systemImage:role:action:)**：创建一个具有指定角色的按钮，该按钮的标签由本地化字符串键和系统图像生成。


---
source: https://developer.apple.com/documentation/SwiftUI/Button/init(role:action:label:)
crawled: 2025-12-01T02:38:54Z
---

# init(role:action:label:)

**Initializer**

Creates a button with a specified role that displays a custom label.

## Declaration

```swift
@preconcurrency nonisolated init(role: ButtonRole?, action: @escaping @MainActor () -> Void, @ViewBuilder label: () -> Label)
```

## Parameters

- **role**: An optional semantic role that describes the button. A value of `nil` means that the button doesn’t have an assigned role.
- **action**: The action to perform when the user interacts with the button.
- **label**: A view that describes the purpose of the button’s `action`.

## Creating a button with a role

- **init(_:role:action:)**: Creates a button with a specified role that generates its label from a localized string key.
- **init(_:image:role:action:)**: Creates a button with a specified role that generates its label from a localized string key and an image resource.
- **init(_:systemImage:role:action:)**: Creates a button with a specified role that generates its label from a localized string key and a system image.

