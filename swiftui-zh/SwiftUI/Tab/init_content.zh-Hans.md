---
来源： https://developer.apple.com/documentation/SwiftUI/Tab/init(内容：)
抓取时间： 2025-12-01T00:43:36Z
---

# init(content:)

**Initializer**

创建一个新标签页，可在标签视图中使用，标签页为空。

## 声明

```swift
init(@ViewBuilder content: () -> Content) where Label == EmptyView
```

## 参数

- **content**：选项卡的视图内容。

## 创建标签页

- **init(value:content:)**：创建一个新标签页，可以在标签页视图中使用，标签页为空。
- **init(role:content:)**：创建一个可在标签视图中使用的新标签页，标签为空。
- **init(value:role:content:)**：创建新标签页，标签由角色推断。


---
source: https://developer.apple.com/documentation/SwiftUI/Tab/init(content:)
crawled: 2025-12-01T00:43:36Z
---

# init(content:)

**Initializer**

Creates a new tab that you can use in a tab view, with an empty label.

## Declaration

```swift
init(@ViewBuilder content: () -> Content) where Label == EmptyView
```

## Parameters

- **content**: The view content of the tab.

## Creating a tab

- **init(value:content:)**: Creates a new tab that you can use in a tab view, with an empty label.
- **init(role:content:)**: Creates a new tab that you can use in a tab view, with an empty label.
- **init(value:role:content:)**: Creates a new tab with a label inferred from the role.

