--- 来源：https://developer.apple.com/documentation/SwiftUI/Menu/init(_:systemImage:content:)

抓取时间：2025-12-03T05:42:52Z

---

# init(_:systemImage:content:)

**Initializer**

创建一个菜单，该菜单的标签由本地化的字符串键和系统图像生成。

## 声明

```swift
nonisolated init(_ titleKey: LocalizedStringKey, systemImage: String, @ViewBuilder content: () -> Content)
```

## 参数

- **titleKey**：链接本地化标题的键，用于描述菜单的内容。

- **systemImage**：要查找的图像资源的名称。

- **content**：一组菜单项。

## 根据内容创建菜单

- **init(_:content:)**：创建一个菜单，其标签由本地化字符串键生成。

- **init(content:label:)**：创建一个带有自定义标签的菜单。

- **init(_:image:content:)**：创建一个菜单，其标签由本地化字符串键和图像资源生成。


---
source: https://developer.apple.com/documentation/SwiftUI/Menu/init(_:systemImage:content:)
crawled: 2025-12-03T05:42:52Z
---

# init(_:systemImage:content:)

**Initializer**

Creates a menu that generates its label from a localized string key and system image.

## Declaration

```swift
nonisolated init(_ titleKey: LocalizedStringKey, systemImage: String, @ViewBuilder content: () -> Content)
```

## Parameters

- **titleKey**: The key for the link’s localized title, which describes the contents of the menu.
- **systemImage**: The name of the image resource to lookup.
- **content**: A group of menu items.

## Creating a menu from content

- **init(_:content:)**: Creates a menu that generates its label from a localized string key.
- **init(content:label:)**: Creates a menu with a custom label.
- **init(_:image:content:)**: Creates a menu that generates its label from a localized string key and image resource.

