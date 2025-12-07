---
来源：https://developer.apple.com/documentation/SwiftUI/Tab/init(角色：内容：标签：)
抓取时间：2025-12-02T20:59:40Z
---

# init(role:content:label:)

**Initializer**

创建带有标签的新标签页，可在标签页视图中使用。

## 声明

```swift
init(role: TabRole?, @ViewBuilder content: () -> Content, @ViewBuilder label: () -> Label)
```

## 参数

- **role**：定义选项卡语义目的的角色。
- **content**：选项卡的视图内容。
- **label**：标签页的视图内容：标签页的标签项的标签。

## 创建带标签的选项卡

- **init(content:label:)**：创建带有标签的新标签页，可以在标签视图中使用。
- **init(value:content:label:)**：**init(value:content:label:)**： 创建带有标签的新选项卡，可在选项卡视图中使用。
- **init(value:role:content:label:)**：创建带有标签的新选项卡，可在选项卡视图中使用。


---
source: https://developer.apple.com/documentation/SwiftUI/Tab/init(role:content:label:)
crawled: 2025-12-02T20:59:40Z
---

# init(role:content:label:)

**Initializer**

Creates a new tab with a label that you can use in a tab view.

## Declaration

```swift
init(role: TabRole?, @ViewBuilder content: () -> Content, @ViewBuilder label: () -> Label)
```

## Parameters

- **role**: The role defining the semantic purpose of the tab.
- **content**: The view content of the tab.
- **label**: The label for the tab’s tab item.

## Creating a tab with label

- **init(content:label:)**: Creates a new tab with a label that you can use in a tab view.
- **init(value:content:label:)**: Creates a new tab with a label that you can use in a tab view.
- **init(value:role:content:label:)**: Creates a new tab with a label that you can use in a tab view.

