--- 来源：https://developer.apple.com/documentation/SwiftUI/Menu/init(_:content:)

抓取时间：2025-12-01T10:31:59Z

---

# init(_:content:)

**Initializer**

创建一个菜单，其标签由本地化字符串键生成。

## 声明

```swift
nonisolated init(_ titleKey: LocalizedStringKey, @ViewBuilder content: () -> Content) where Label == Text
```

## 参数

- **titleKey**：链接本地化标题的键，用于描述菜单内容。

- **content**：一组菜单项。

## 从内容创建菜单

- **init(content:label:)**：创建一个带有自定义标签的菜单。

- **init(_:image:content:)**：创建一个菜单，该菜单的标签由本地化的字符串键和图像资源生成。

- **init(_:systemImage:content:)**：创建一个菜单，该菜单的标签由本地化的字符串键和系统图像生成。


---
source: https://developer.apple.com/documentation/SwiftUI/Menu/init(_:content:)
crawled: 2025-12-01T10:31:59Z
---

# init(_:content:)

**Initializer**

Creates a menu that generates its label from a localized string key.

## Declaration

```swift
nonisolated init(_ titleKey: LocalizedStringKey, @ViewBuilder content: () -> Content) where Label == Text
```

## Parameters

- **titleKey**: The key for the link’s localized title, which describes the contents of the menu.
- **content**: A group of menu items.

## Creating a menu from content

- **init(content:label:)**: Creates a menu with a custom label.
- **init(_:image:content:)**: Creates a menu that generates its label from a localized string key and image resource.
- **init(_:systemImage:content:)**: Creates a menu that generates its label from a localized string key and system image.

