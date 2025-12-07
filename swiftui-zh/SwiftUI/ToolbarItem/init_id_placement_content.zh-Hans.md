--- 来源：https://developer.apple.com/documentation/SwiftUI/ToolbarItem/init(id:placement:content:)

抓取时间：2025-12-03T06:02:58Z

---

# init(id:placement:content:)

**Initializer**

创建一个具有指定位置和内容的工具栏项，允许用户进行自定义。

## 声明

```swift
nonisolated init(id: String, placement: ToolbarItemPlacement = .automatic, @ViewBuilder content: () -> Content)
```

## 参数

- **id**：此项目的唯一标识符。

- **placement**：此项目应放置在工具栏的哪个部分。

- **content**：此项目的内容。

## 创建工具栏项

- **init(placement:content:)**：创建具有指定位置和内容的工具栏项。

- **init(id:placement:showsByDefault:content:)**：创建具有指定位置和内容的工具栏项，并允许用户进行自定义。


---
source: https://developer.apple.com/documentation/SwiftUI/ToolbarItem/init(id:placement:content:)
crawled: 2025-12-03T06:02:58Z
---

# init(id:placement:content:)

**Initializer**

Creates a toolbar item with the specified placement and content, which allows for user customization.

## Declaration

```swift
nonisolated init(id: String, placement: ToolbarItemPlacement = .automatic, @ViewBuilder content: () -> Content)
```

## Parameters

- **id**: A unique identifier for this item.
- **placement**: Which section of the toolbar the item should be placed in.
- **content**: The content of the item.

## Creating a toolbar item

- **init(placement:content:)**: Creates a toolbar item with the specified placement and content.
- **init(id:placement:showsByDefault:content:)**: Creates a toolbar item with the specified placement and content, which allows for user customization.

