--- 来源：https://developer.apple.com/documentation/SwiftUI/Menu/init(_:content:primaryAction:)

抓取时间：2025-12-01T10:32:03Z

---

# init(_:content:primaryAction:)

**Initializer**

创建一个带有自定义主操作的菜单，该操作的标签由本地化字符串键生成。

## 声明

```swift
nonisolated init(_ titleKey: LocalizedStringKey, @ViewBuilder content: () -> Content, primaryAction: @escaping () -> Void) where Label == Text
```

## 参数

- **titleKey**：链接本地化标题的键，用于描述菜单内容。

- **content**：一组菜单项。

- **primaryAction**：与菜单进行主要交互时要执行的操作。

## 创建带有主操作的菜单

- **init(content:label:primaryAction:)**：创建一个带有自定义主操作和自定义标签的菜单。

- **init(_:image:content:primaryAction:)**：创建一个带有自定义主操作的菜单，该菜单的标签由本地化字符串键生成。

- **init(_:systemImage:content:primaryAction:)**：创建一个带有自定义主操作的菜单，该菜单的标签由本地化字符串键和系统图像生成。


---
source: https://developer.apple.com/documentation/SwiftUI/Menu/init(_:content:primaryAction:)
crawled: 2025-12-01T10:32:03Z
---

# init(_:content:primaryAction:)

**Initializer**

Creates a menu with a custom primary action that generates its label from a localized string key.

## Declaration

```swift
nonisolated init(_ titleKey: LocalizedStringKey, @ViewBuilder content: () -> Content, primaryAction: @escaping () -> Void) where Label == Text
```

## Parameters

- **titleKey**: The key for the link’s localized title, which describes the contents of the menu.
- **content**: A group of menu items.
- **primaryAction**: The action to perform on primary interaction with the menu.

## Creating a menu with a primary action

- **init(content:label:primaryAction:)**: Creates a menu with a custom primary action and custom label.
- **init(_:image:content:primaryAction:)**: Creates a menu with a custom primary action that generates its label from a localized string key.
- **init(_:systemImage:content:primaryAction:)**: Creates a menu with a custom primary action that generates its label from a localized string key and system image.

