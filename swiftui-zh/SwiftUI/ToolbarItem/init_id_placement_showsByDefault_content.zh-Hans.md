--- 来源：https://developer.apple.com/documentation/SwiftUI/ToolbarItem/init(id:placement:showsByDefault:content:)

抓取时间：2025-12-03T06:02:59Z

---

# init(id:placement:showsByDefault:content:)

**Initializer**

创建一个具有指定位置和内容的工具栏项，允许用户进行自定义。

## 声明

```swift
nonisolated init(id: String, placement: ToolbarItemPlacement = .automatic, showsByDefault: Bool, @ViewBuilder content: () -> Content)
```

## 参数

- **id**：此项目的唯一标识符。

- **placement**：此项目应放置在工具栏的哪个部分。

- **showsByDefault**：此项目是否默认显示在工具栏中，还是仅在用户通过自定义显式添加时才显示。

- **content**：工具栏项的内容。

## 创建工具栏项

- **init(placement:content:)**：创建具有指定位置和内容的工具栏项。

- **init(id:placement:content:)**：创建具有指定位置和内容的工具栏项，允许用户自定义。


---
source: https://developer.apple.com/documentation/SwiftUI/ToolbarItem/init(id:placement:showsByDefault:content:)
crawled: 2025-12-03T06:02:59Z
---

# init(id:placement:showsByDefault:content:)

**Initializer**

Creates a toolbar item with the specified placement and content, which allows for user customization.

## Declaration

```swift
nonisolated init(id: String, placement: ToolbarItemPlacement = .automatic, showsByDefault: Bool, @ViewBuilder content: () -> Content)
```

## Parameters

- **id**: A unique identifier for this item.
- **placement**: Which section of the toolbar the item should be placed in.
- **showsByDefault**: Whether the item appears by default in the toolbar, or only shows if the user explicitly adds it via customization.
- **content**: The content of the item.

## Creating a toolbar item

- **init(placement:content:)**: Creates a toolbar item with the specified placement and content.
- **init(id:placement:content:)**: Creates a toolbar item with the specified placement and content, which allows for user customization.

