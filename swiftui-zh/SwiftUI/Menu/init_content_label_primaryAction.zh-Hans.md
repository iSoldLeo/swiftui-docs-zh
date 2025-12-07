--- 来源：https://developer.apple.com/documentation/SwiftUI/Menu/init(content:label:primaryAction:)

抓取时间：2025-12-03T05:42:53Z

---

# init(content:label:primaryAction:)

**Initializer**

创建一个带有自定义主操作和自定义标签的菜单。

## 声明

```swift
nonisolated init(@ViewBuilder content: () -> Content, @ViewBuilder label: () -> Label, primaryAction: @escaping () -> Void)
```

## 参数

- **content**：一组菜单项。

- **label**：描述菜单内容的视图。

- **primaryAction**：与菜单进行主交互时要执行的操作。

## 创建带有主操作的菜单

- **init(_:content:primaryAction:)**：创建一个带有自定义主操作的菜单，该菜单的标签由本地化字符串键生成。

- **init(_:image:content:primaryAction:)**：创建一个带有自定义主操作的菜单，该菜单的标签由本地化字符串键生成。

- **init(_:systemImage:content:primaryAction:)**：创建一个带有自定义主操作的菜单，该菜单的标签由本地化字符串键和系统图像生成。


---
source: https://developer.apple.com/documentation/SwiftUI/Menu/init(content:label:primaryAction:)
crawled: 2025-12-03T05:42:53Z
---

# init(content:label:primaryAction:)

**Initializer**

Creates a menu with a custom primary action and custom label.

## Declaration

```swift
nonisolated init(@ViewBuilder content: () -> Content, @ViewBuilder label: () -> Label, primaryAction: @escaping () -> Void)
```

## Parameters

- **content**: A group of menu items.
- **label**: A view describing the content of the menu.
- **primaryAction**: The action to perform on primary interaction with the menu.

## Creating a menu with a primary action

- **init(_:content:primaryAction:)**: Creates a menu with a custom primary action that generates its label from a localized string key.
- **init(_:image:content:primaryAction:)**: Creates a menu with a custom primary action that generates its label from a localized string key.
- **init(_:systemImage:content:primaryAction:)**: Creates a menu with a custom primary action that generates its label from a localized string key and system image.

