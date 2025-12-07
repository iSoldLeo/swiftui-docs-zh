---
来源：https://developer.apple.com/documentation/SwiftUI/ToolbarItemGroup/init(位置:内容:标签:)
抓取时间：2025-12-03T06:03:00Z
---

# init(placement:content:label:)

**Initializer**

用指定的位置、内容和描述该内容的标签创建工具栏项目组。

### 声明

```swift
nonisolated init<C, L>(placement: ToolbarItemPlacement = .automatic, @ViewBuilder content: () -> C, @ViewBuilder label: () -> L) where Content == LabeledToolbarItemGroupContent<C, L>, C : View, L : View
```

## 参数

- **placement**：项目应放在工具栏的哪个部分。
- **content**：项目的内容。
- **label**：描述项目内容的标签。

## 讨论

提供标签的工具栏项目组将其内容封装在一个[ControlGroup](../ControlGroup.zh-Hans.md)内，使内容可以折叠成一个菜单，并根据可用空间显示其内容。

## 创建工具栏项目组

- **init(placement:content:)**：创建具有指定位置和内容的工具栏项目组。


---
source: https://developer.apple.com/documentation/SwiftUI/ToolbarItemGroup/init(placement:content:label:)
crawled: 2025-12-03T06:03:00Z
---

# init(placement:content:label:)

**Initializer**

Creates a toolbar item group with the specified placement, content, and a label describing that content.

## Declaration

```swift
nonisolated init<C, L>(placement: ToolbarItemPlacement = .automatic, @ViewBuilder content: () -> C, @ViewBuilder label: () -> L) where Content == LabeledToolbarItemGroupContent<C, L>, C : View, L : View
```

## Parameters

- **placement**: Which section of the toolbar the item should be placed in.
- **content**: The content of the item.
- **label**: The label describing the content of the item.

## Discussion

A toolbar item group provided a label wraps its content within a [ControlGroup](../ControlGroup.zh-Hans.md) which allows the content to collapse down into a menu that presents its content based on available space.

## Creating a toolbar item group

- **init(placement:content:)**: Creates a toolbar item group with a specified placement and content.

