--- 来源：https://developer.apple.com/documentation/SwiftUI/Menu/init(content:label:)

抓取时间：2025-12-03T05:42:50Z

---

# init(content:label:)

**Initializer**

创建一个带有自定义标签的菜单。

## 声明

```swift
nonisolated init(@ViewBuilder content: () -> Content, @ViewBuilder label: () -> Label)
```

## 参数

- **content**：一组菜单项。

- **label**：描述菜单内容的视图。

## 根据内容创建菜单

- **init(_:content:)**：创建一个菜单，其标签由本地化字符串键生成。

- **init(_:image:content:)**：创建一个菜单，该菜单的标签由本地化的字符串键和图像资源生成。

- **init(_:systemImage:content:)**：创建一个菜单，该菜单的标签由本地化的字符串键和系统图像生成。


---
source: https://developer.apple.com/documentation/SwiftUI/Menu/init(content:label:)
crawled: 2025-12-03T05:42:50Z
---

# init(content:label:)

**Initializer**

Creates a menu with a custom label.

## Declaration

```swift
nonisolated init(@ViewBuilder content: () -> Content, @ViewBuilder label: () -> Label)
```

## Parameters

- **content**: A group of menu items.
- **label**: A view describing the content of the menu.

## Creating a menu from content

- **init(_:content:)**: Creates a menu that generates its label from a localized string key.
- **init(_:image:content:)**: Creates a menu that generates its label from a localized string key and image resource.
- **init(_:systemImage:content:)**: Creates a menu that generates its label from a localized string key and system image.

