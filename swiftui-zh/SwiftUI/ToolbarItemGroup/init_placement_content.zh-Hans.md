---
来源：https://developer.apple.com/documentation/SwiftUI/ToolbarItemGroup/init(位置:内容:)
抓取时间： 2025-12-03T06:02:59Z
---

# init(placement:content:)

**Initializer**

以指定的位置和内容创建工具栏项目组。

### 声明

```swift
init(placement: ToolbarItemPlacement = .automatic, @ViewBuilder content: () -> Content)
```

## 讨论

- 放置：工具栏中所有提供的 `ToolbarItem` 应放置在哪个部分。
- content（内容）：组的内容。在`ViewBuilder`中指定的每个视图都将在工具栏中拥有自己的`ToolbarItem`。

## 创建工具栏项目组

- **init(placement:content:label:)**：以指定的位置、内容和描述该内容的标签创建工具栏项目组。


---
source: https://developer.apple.com/documentation/SwiftUI/ToolbarItemGroup/init(placement:content:)
crawled: 2025-12-03T06:02:59Z
---

# init(placement:content:)

**Initializer**

Creates a toolbar item group with a specified placement and content.

## Declaration

```swift
init(placement: ToolbarItemPlacement = .automatic, @ViewBuilder content: () -> Content)
```

## Discussion

- placement: Which section of the toolbar all of its vended `ToolbarItem`s should be placed in.
- content: The content of the group. Each view specified in the `ViewBuilder` will be given its own `ToolbarItem` in the toolbar.

## Creating a toolbar item group

- **init(placement:content:label:)**: Creates a toolbar item group with the specified placement, content, and a label describing that content.

