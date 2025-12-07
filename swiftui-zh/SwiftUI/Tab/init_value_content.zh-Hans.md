---
来源：https://developer.apple.com/documentation/SwiftUI/Tab/init(value:content:)
抓取时间： 2025-12-02T20:59:35Z
---

# init(value:content:)

**Initializer**

创建一个新标签页，可在标签视图中使用，标签页为空。

## 声明

```swift
nonisolated init(value: Value, @ViewBuilder content: () -> Content) where Label == EmptyView
```

## 参数

- **value**：选择此选项卡的 `selection` 值。
- **content**：选项卡的视图内容。

## 创建标签页

- **init(content:)**：创建一个新标签页，可以在标签页视图中使用，标签页为空。
- **init(role:content:)**：创建一个可在标签视图中使用的新标签页，标签为空。
- **init(value:role:content:)**：创建一个新标签页，标签由角色推断。


---
source: https://developer.apple.com/documentation/SwiftUI/Tab/init(value:content:)
crawled: 2025-12-02T20:59:35Z
---

# init(value:content:)

**Initializer**

Creates a new tab that you can use in a tab view, with an empty label.

## Declaration

```swift
nonisolated init(value: Value, @ViewBuilder content: () -> Content) where Label == EmptyView
```

## Parameters

- **value**: The `selection` value which selects this tab.
- **content**: The view content of the tab.

## Creating a tab

- **init(content:)**: Creates a new tab that you can use in a tab view, with an empty label.
- **init(role:content:)**: Creates a new tab that you can use in a tab view, with an empty label.
- **init(value:role:content:)**: Creates a new tab with a label inferred from the role.

