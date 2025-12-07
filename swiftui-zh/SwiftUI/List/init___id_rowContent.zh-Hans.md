--- 来源：https://developer.apple.com/documentation/SwiftUI/List/init(_:id:rowContent:)

抓取时间：2025-12-03T05:42:41Z

---

# init(_:id:rowContent:)

**Initializer**

创建一个列表，该列表基于指向底层数据标识符的键路径来标识其行。

## 声明

```swift
@MainActor @preconcurrency init<Data, ID, RowContent>(_ data: Binding<Data>, id: KeyPath<Data.Element, ID>, @ViewBuilder rowContent: @escaping (Binding<Data.Element>) -> RowContent) where Content == ForEach<LazyMapSequence<Data.Indices, (Data.Index, ID)>, ID, RowContent>, Data : MutableCollection, Data : RandomAccessCollection, ID : Hashable, RowContent : View, Data.Index : Hashable
```

## 参数

- **data**：用于填充列表的数据。

- **id**：指向数据模型标识符的键路径。

- **rowContent**：一个视图构建器，用于创建列表中单行的视图。

## 从枚举数据创建列表

- **init(_:rowContent:)**：创建一个列表，该列表根据底层可识别数据集合按需计算其行。

- **init(_:selection:rowContent:)**：创建一个列表，该列表根据底层可识别数据集合按需计算其行，并允许用户选择性地选择单行。

- **init(_:id:selection:rowContent:)**：创建一个列表，该列表基于指向底层数据标识符的键路径来标识其行，并允许用户选择性地选择单行。


---
source: https://developer.apple.com/documentation/SwiftUI/List/init(_:id:rowContent:)
crawled: 2025-12-03T05:42:41Z
---

# init(_:id:rowContent:)

**Initializer**

Creates a list that identifies its rows based on a key path to the identifier of the underlying data.

## Declaration

```swift
@MainActor @preconcurrency init<Data, ID, RowContent>(_ data: Binding<Data>, id: KeyPath<Data.Element, ID>, @ViewBuilder rowContent: @escaping (Binding<Data.Element>) -> RowContent) where Content == ForEach<LazyMapSequence<Data.Indices, (Data.Index, ID)>, ID, RowContent>, Data : MutableCollection, Data : RandomAccessCollection, ID : Hashable, RowContent : View, Data.Index : Hashable
```

## Parameters

- **data**: The data for populating the list.
- **id**: The key path to the data model’s identifier.
- **rowContent**: A view builder that creates the view for a single row of the list.

## Creating a list from enumerated data

- **init(_:rowContent:)**: Creates a list that computes its rows on demand from an underlying collection of identifiable data.
- **init(_:selection:rowContent:)**: Creates a list that computes its rows on demand from an underlying collection of identifiable data, optionally allowing users to select a single row.
- **init(_:id:selection:rowContent:)**: Creates a list that identifies its rows based on a key path to the identifier of the underlying data, optionally allowing users to select a single row.

