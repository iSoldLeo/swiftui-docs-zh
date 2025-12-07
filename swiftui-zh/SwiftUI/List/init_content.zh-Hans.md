--- 来源：https://developer.apple.com/documentation/SwiftUI/List/init(content:)

抓取时间：2025-12-01T10:31:46Z

---

# init(content:)

**Initializer**

创建一个包含给定内容的列表。

## 声明

```swift
@MainActor @preconcurrency init(@ViewBuilder content: () -> Content)
```

## 参数

- **content**：列表的内容。

## 从一组视图创建列表

- **init(selection:content:)**：创建一个包含给定内容的列表，支持选择单个行且无法取消选择。


---
source: https://developer.apple.com/documentation/SwiftUI/List/init(content:)
crawled: 2025-12-01T10:31:46Z
---

# init(content:)

**Initializer**

Creates a list with the given content.

## Declaration

```swift
@MainActor @preconcurrency init(@ViewBuilder content: () -> Content)
```

## Parameters

- **content**: The content of the list.

## Creating a list from a set of views

- **init(selection:content:)**: Creates a list with the given content that supports selecting a single row that cannot be deselected.

