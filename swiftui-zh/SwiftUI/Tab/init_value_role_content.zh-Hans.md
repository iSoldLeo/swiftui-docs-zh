---
来源：https://developer.apple.com/documentation/swiftui/tab/init(value:role:content:)
抓取时间： 2025-12-02T16:16:20Z
---

# init(value:role:content:)

**Initializer**

创建一个新标签页，标签由角色推断得出。

## 声明

```swift
nonisolated init(value: Value, role: TabRole?, @ViewBuilder content: () -> Content) where Label == DefaultTabLabel
```

## 参数

- **value**：选择此选项卡的 `selection` 值。
- **role**：定义标签页语义目的的`role`。
- **content**：标签页的视图内容。

## 创建标签页

- **init(content:)**：创建一个新标签页，可以在标签页视图中使用，标签页为空。
- **init(value:content:)**：创建一个可在选项卡视图中使用的新选项卡，标签为空。
- **init(role:content:)**：创建一个可在标签视图中使用的新标签页，标签为空。


---
source: https://developer.apple.com/documentation/swiftui/tab/init(value:role:content:)
crawled: 2025-12-02T16:16:20Z
---

# init(value:role:content:)

**Initializer**

Creates a new tab with a label inferred from the role.

## Declaration

```swift
nonisolated init(value: Value, role: TabRole?, @ViewBuilder content: () -> Content) where Label == DefaultTabLabel
```

## Parameters

- **value**: The `selection` value which selects this tab.
- **role**: The `role` defining the semantic purpose of the tab.
- **content**: The view content of the tab.

## Creating a tab

- **init(content:)**: Creates a new tab that you can use in a tab view, with an empty label.
- **init(value:content:)**: Creates a new tab that you can use in a tab view, with an empty label.
- **init(role:content:)**: Creates a new tab that you can use in a tab view, with an empty label.

