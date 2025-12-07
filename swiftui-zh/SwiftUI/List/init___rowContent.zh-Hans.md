--- 来源：https://developer.apple.com/documentation/SwiftUI/List/init(_:rowContent:)

抓取时间：2025-12-01T10:31:48Z

---

# init(_:rowContent:)

**Initializer**

创建一个列表，该列表会根据底层可识别数据集合按需计算其行。

## 声明

```swift
@MainActor @preconcurrency init<Data, RowContent>(_ data: Binding<Data>, @ViewBuilder rowContent: @escaping (Binding<Data.Element>) -> RowContent) where Content == ForEach<LazyMapSequence<Data.Indices, (Data.Index, Data.Element.ID)>, Data.Element.ID, RowContent>, Data : MutableCollection, Data : RandomAccessCollection, RowContent : View, Data.Element : Identifiable, Data.Index : Hashable
```

## 参数

- **data**：用于计算列表的可识别数据集合。

- **rowContent**：一个视图构建器，用于创建列表中单行的视图。

## 从枚举数据创建列表

- **init(_:selection:rowContent:)**：创建一个列表，该列表根据底层可识别数据集合按需计算行，并允许用户选择单行。

- **init(_:id:rowContent:)**：创建一个列表，该列表基于指向底层数据标识符的键路径来标识其行。

- **init(_:id:selection:rowContent:)**：创建一个列表，该列表基于指向底层数据标识符的键路径来标识其行，并允许用户选择单行。


---
source: https://developer.apple.com/documentation/SwiftUI/List/init(_:rowContent:)
crawled: 2025-12-01T10:31:48Z
---

# init(_:rowContent:)

**Initializer**

Creates a list that computes its rows on demand from an underlying collection of identifiable data.

## Declaration

```swift
@MainActor @preconcurrency init<Data, RowContent>(_ data: Binding<Data>, @ViewBuilder rowContent: @escaping (Binding<Data.Element>) -> RowContent) where Content == ForEach<LazyMapSequence<Data.Indices, (Data.Index, Data.Element.ID)>, Data.Element.ID, RowContent>, Data : MutableCollection, Data : RandomAccessCollection, RowContent : View, Data.Element : Identifiable, Data.Index : Hashable
```

## Parameters

- **data**: A collection of identifiable data for computing the list.
- **rowContent**: A view builder that creates the view for a single row of the list.

## Creating a list from enumerated data

- **init(_:selection:rowContent:)**: Creates a list that computes its rows on demand from an underlying collection of identifiable data, optionally allowing users to select a single row.
- **init(_:id:rowContent:)**: Creates a list that identifies its rows based on a key path to the identifier of the underlying data.
- **init(_:id:selection:rowContent:)**: Creates a list that identifies its rows based on a key path to the identifier of the underlying data, optionally allowing users to select a single row.

