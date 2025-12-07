--- 来源：https://developer.apple.com/documentation/SwiftUI/List/init(selection:content:)

抓取时间：2025-12-03T05:42:39Z

---

# init(selection:content:)

**Initializer**

创建一个包含给定内容的列表，支持选中单行且无法取消选中。

## 声明

```swift
@MainActor @preconcurrency init(selection: Binding<SelectionValue>, @ViewBuilder content: () -> Content)
```

## 参数

- **selection**：绑定到已选中的行。

- **content**：列表的内容。

## 从一组视图创建列表

- **init(content:)**：创建一个包含给定内容的列表。


---
source: https://developer.apple.com/documentation/SwiftUI/List/init(selection:content:)
crawled: 2025-12-03T05:42:39Z
---

# init(selection:content:)

**Initializer**

Creates a list with the given content that supports selecting a single row that cannot be deselected.

## Declaration

```swift
@MainActor @preconcurrency init(selection: Binding<SelectionValue>, @ViewBuilder content: () -> Content)
```

## Parameters

- **selection**: A binding to a selected row.
- **content**: The content of the list.

## Creating a list from a set of views

- **init(content:)**: Creates a list with the given content.

