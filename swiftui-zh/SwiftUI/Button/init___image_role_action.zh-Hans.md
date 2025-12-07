--- 来源：https://developer.apple.com/documentation/SwiftUI/Button/init(_:image:role:action:)

抓取时间：2025-12-01T02:38:55Z

---

# init(_:image:role:action:)

**Initializer**

创建一个具有指定角色的按钮，该按钮的标签由本地化字符串键和图像资源生成。

## 声明

```swift
@preconcurrency nonisolated init(_ titleKey: LocalizedStringKey, image: ImageResource, role: ButtonRole?, action: @escaping @MainActor () -> Void)
```

## 参数

- **titleKey**：按钮本地化标题的键，用于描述按钮的用途。

- **image**：要查找的图像资源。

- **role**：描述按钮的可选语义角色。 `nil` 值表示该按钮未分配角色。

- **action**：用户触发按钮时要执行的操作。

## 讨论

此初始化程序会代表您创建一个 [Label](../Label.zh-Hans.md) 视图，并将本地化键的处理方式与 [init(_:tableName:bundle:comment:)](../Text/init___tableName_bundle_comment.zh-Hans.md) 类似。有关字符串本地化的更多信息，请参阅 [Text](../Text.zh-Hans.md)。

## 创建具有角色的按钮

- **init(role:action:label:)**：创建一个具有指定角色的按钮，该按钮会显示自定义标签。

- **init(_:role:action:)**：创建一个具有指定角色的按钮，该按钮会根据本地化字符串键生成其标签。

- **init(_:systemImage:role:action:)**：创建一个具有指定角色的按钮，该按钮的标签由本地化字符串键和系统图像生成。


---
source: https://developer.apple.com/documentation/SwiftUI/Button/init(_:image:role:action:)
crawled: 2025-12-01T02:38:55Z
---

# init(_:image:role:action:)

**Initializer**

Creates a button with a specified role that generates its label from a localized string key and an image resource.

## Declaration

```swift
@preconcurrency nonisolated init(_ titleKey: LocalizedStringKey, image: ImageResource, role: ButtonRole?, action: @escaping @MainActor () -> Void)
```

## Parameters

- **titleKey**: The key for the button’s localized title, that describes the purpose of the button’s `action`.
- **image**: The image resource to lookup.
- **role**: An optional semantic role describing the button. A value of `nil` means that the button doesn’t have an assigned role.
- **action**: The action to perform when the user triggers the button.

## Discussion

This initializer creates a [Label](../Label.zh-Hans.md) view on your behalf, and treats the localized key similar to [init(_:tableName:bundle:comment:)](../Text/init___tableName_bundle_comment.zh-Hans.md). See [Text](../Text.zh-Hans.md) for more information about localizing strings.

## Creating a button with a role

- **init(role:action:label:)**: Creates a button with a specified role that displays a custom label.
- **init(_:role:action:)**: Creates a button with a specified role that generates its label from a localized string key.
- **init(_:systemImage:role:action:)**: Creates a button with a specified role that generates its label from a localized string key and a system image.

