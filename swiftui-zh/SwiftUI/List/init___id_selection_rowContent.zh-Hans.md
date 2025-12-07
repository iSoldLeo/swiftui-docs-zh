--- 来源：https://developer.apple.com/documentation/SwiftUI/List/init(_:id:selection:rowContent:)

抓取时间：2025-12-01T10:31:50Z

---

# init(_:id:selection:rowContent:)

**Initializer**

创建一个列表，该列表基于指向底层数据标识符的键路径来标识其行，并允许用户选择单行。

## 声明

```swift
@MainActor @preconcurrency init<Data, ID, RowContent>(_ data: Binding<Data>, id: KeyPath<Data.Element, ID>, selection: Binding<SelectionValue?>?, @ViewBuilder rowContent: @escaping (Binding<Data.Element>) -> RowContent) where Content == ForEach<LazyMapSequence<Data.Indices, (Data.Index, ID)>, ID, RowContent>, Data : MutableCollection, Data : RandomAccessCollection, ID : Hashable, RowContent : View, Data.Index : Hashable
```

## 参数

- **data**：用于填充列表的数据。

- **id**：指向数据模型标识符的键路径。

- **selection**：与所选值绑定。

- **rowContent**：用于创建列表中单行视图的视图构建器。

## 从枚举数据创建列表

- **init(_:rowContent:)**：创建一个列表，该列表根据底层可识别数据集合按需计算其行。

- **init(_:selection:rowContent:)**：创建一个列表，该列表根据底层可识别数据集合按需计算其行，并允许用户选择单行。

- **init(_:id:rowContent:)**：创建一个列表，该列表根据指向底层数据标识符的键路径来标识其行。


---
source: https://developer.apple.com/documentation/SwiftUI/List/init(_:id:selection:rowContent:)
crawled: 2025-12-01T10:31:50Z
---

# init(_:id:selection:rowContent:)

**Initializer**

Creates a list that identifies its rows based on a key path to the identifier of the underlying data, optionally allowing users to select a single row.

## Declaration

```swift
@MainActor @preconcurrency init<Data, ID, RowContent>(_ data: Binding<Data>, id: KeyPath<Data.Element, ID>, selection: Binding<SelectionValue?>?, @ViewBuilder rowContent: @escaping (Binding<Data.Element>) -> RowContent) where Content == ForEach<LazyMapSequence<Data.Indices, (Data.Index, ID)>, ID, RowContent>, Data : MutableCollection, Data : RandomAccessCollection, ID : Hashable, RowContent : View, Data.Index : Hashable
```

## Parameters

- **data**: The data for populating the list.
- **id**: The key path to the data model’s identifier.
- **selection**: A binding to a selected value.
- **rowContent**: A view builder that creates the view for a single row of the list.

## Creating a list from enumerated data

- **init(_:rowContent:)**: Creates a list that computes its rows on demand from an underlying collection of identifiable data.
- **init(_:selection:rowContent:)**: Creates a list that computes its rows on demand from an underlying collection of identifiable data, optionally allowing users to select a single row.
- **init(_:id:rowContent:)**: Creates a list that identifies its rows based on a key path to the identifier of the underlying data.

