--- 来源：https://developer.apple.com/documentation/SwiftUI/ToolbarItem/init(placement:content:)

抓取时间：2025-12-03T06:02:57Z

---

# init(placement:content:)

**Initializer**

创建一个具有指定位置和内容的工具栏项。

## 声明

```swift
nonisolated init(placement: ToolbarItemPlacement = .automatic, @ViewBuilder content: () -> Content)
```

## 参数

- **placement**：工具栏项应放置在哪个部分。

- **content**：工具栏项的内容。

## 创建工具栏项

- **init(id:placement:content:)**：创建一个具有指定位置和内容的工具栏项，允许用户进行自定义。

- **init(id:placement:showsByDefault:content:)**：创建具有指定位置和内容的工具栏项，允许用户进行自定义。


---
source: https://developer.apple.com/documentation/SwiftUI/ToolbarItem/init(placement:content:)
crawled: 2025-12-03T06:02:57Z
---

# init(placement:content:)

**Initializer**

Creates a toolbar item with the specified placement and content.

## Declaration

```swift
nonisolated init(placement: ToolbarItemPlacement = .automatic, @ViewBuilder content: () -> Content)
```

## Parameters

- **placement**: Which section of the toolbar the item should be placed in.
- **content**: The content of the item.

## Creating a toolbar item

- **init(id:placement:content:)**: Creates a toolbar item with the specified placement and content, which allows for user customization.
- **init(id:placement:showsByDefault:content:)**: Creates a toolbar item with the specified placement and content, which allows for user customization.

