---
来源：https://developer.apple.com/documentation/SwiftUI/Tab/init(角色：内容：)
抓取时间： 2025-12-01T00:43:38Z
---

# init(role:content:)

**Initializer**

创建一个新标签页，可在标签视图中使用，标签页为空。

## 声明

```swift
init(role: TabRole?, @ViewBuilder content: () -> Content) where Label == DefaultTabLabel
```

## 参数

- **role**：定义选项卡语义目的的角色。
- **content**：标签页的视图内容。

## 创建标签页

- **init(content:)**：创建一个新标签页，可以在标签页视图中使用，标签页为空。
- **init(value:content:)**：创建一个可在标签视图中使用的新标签页，标签为空。
- **init(value:role:content:)**：创建新标签页，标签由角色推断。


---
source: https://developer.apple.com/documentation/SwiftUI/Tab/init(role:content:)
crawled: 2025-12-01T00:43:38Z
---

# init(role:content:)

**Initializer**

Creates a new tab that you can use in a tab view, with an empty label.

## Declaration

```swift
init(role: TabRole?, @ViewBuilder content: () -> Content) where Label == DefaultTabLabel
```

## Parameters

- **role**: The role defining the semantic purpose of the tab.
- **content**: The view content of the tab.

## Creating a tab

- **init(content:)**: Creates a new tab that you can use in a tab view, with an empty label.
- **init(value:content:)**: Creates a new tab that you can use in a tab view, with an empty label.
- **init(value:role:content:)**: Creates a new tab with a label inferred from the role.

