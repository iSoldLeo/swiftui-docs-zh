--- 来源：https://developer.apple.com/documentation/SwiftUI/List/init(_:selection:rowContent:)

抓取时间：2025-12-01T10:31:48Z

---

# init(_:selection:rowContent:)

**Initializer**

创建一个列表，该列表根据底层可识别数据集合按需计算行，并允许用户选择单行。

## 声明

```swift
@MainActor @preconcurrency init<Data, RowContent>(_ data: Binding<Data>, selection: Binding<SelectionValue?>?, @ViewBuilder rowContent: @escaping (Binding<Data.Element>) -> RowContent) where Content == ForEach<LazyMapSequence<Data.Indices, (Data.Index, Data.Element.ID)>, Data.Element.ID, RowContent>, Data : MutableCollection, Data : RandomAccessCollection, RowContent : View, Data.Element : Identifiable, Data.Index : Hashable
```

## 参数

- **data**：用于计算列表的可识别数据。

- **selection**：绑定到所选值。

- **rowContent**：用于创建列表单行视图的视图构建器。

## 从枚举数据创建列表

- **init(_:rowContent:)**：创建一个列表，该列表根据底层可识别数据集合按需计算其行。

- **init(_:id:rowContent:)**：创建一个列表，该列表基于指向底层数据标识符的键路径来标识其行。

- **init(_:id:selection:rowContent:)**：创建一个列表，该列表基于指向底层数据标识符的键路径来标识其行，并允许用户选择性地选择单行。


---
source: https://developer.apple.com/documentation/SwiftUI/List/init(_:selection:rowContent:)
crawled: 2025-12-01T10:31:48Z
---

# init(_:selection:rowContent:)

**Initializer**

Creates a list that computes its rows on demand from an underlying collection of identifiable data, optionally allowing users to select a single row.

## Declaration

```swift
@MainActor @preconcurrency init<Data, RowContent>(_ data: Binding<Data>, selection: Binding<SelectionValue?>?, @ViewBuilder rowContent: @escaping (Binding<Data.Element>) -> RowContent) where Content == ForEach<LazyMapSequence<Data.Indices, (Data.Index, Data.Element.ID)>, Data.Element.ID, RowContent>, Data : MutableCollection, Data : RandomAccessCollection, RowContent : View, Data.Element : Identifiable, Data.Index : Hashable
```

## Parameters

- **data**: The identifiable data for computing the list.
- **selection**: A binding to a selected value.
- **rowContent**: A view builder that creates the view for a single row of the list.

## Creating a list from enumerated data

- **init(_:rowContent:)**: Creates a list that computes its rows on demand from an underlying collection of identifiable data.
- **init(_:id:rowContent:)**: Creates a list that identifies its rows based on a key path to the identifier of the underlying data.
- **init(_:id:selection:rowContent:)**: Creates a list that identifies its rows based on a key path to the identifier of the underlying data, optionally allowing users to select a single row.

