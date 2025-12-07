--- 来源：https://developer.apple.com/documentation/SwiftUI/List/init(_:id:children:selection:rowContent:)

抓取时间：2025-12-01T10:31:53Z

---

# init(_:id:children:selection:rowContent:)

**Initializer**

创建一个层级列表，该列表基于指向底层数据标识符的键路径来标识其行，并允许用户始终选中且仅选中一行。

## 声明

```swift
@MainActor @preconcurrency init<Data, ID, RowContent>(_ data: Binding<Data>, id: KeyPath<Data.Element, ID>, children: WritableKeyPath<Data.Element, Data?>, selection: Binding<SelectionValue>, @ViewBuilder rowContent: @escaping (Binding<Data.Element>) -> RowContent) where Content == OutlineGroup<Binding<Data>, ID, RowContent, RowContent, DisclosureGroup<RowContent, OutlineSubgroupChildren>>, Data : MutableCollection, Data : RandomAccessCollection, ID : Hashable, RowContent : View
```

## 参数

- **data**：用于填充列表的数据。

- **id**：指向数据模型标识符的键路径。

- **children**：指向属性的键路径，该属性的非 `nil` 值表示 `data` 的子节点。非 `nil` 但为空的值表示一个可以拥有子节点但当前没有子节点的节点，例如文件系统中的空目录。另一方面，如果键路径处的属性为 `nil`，则 `data` 被视为树中的叶节点，就像文件系统中的普通文件一样。

- **selection**：绑定到非可选的已选值。

- **rowContent**：用于创建列表中单行视图的视图构建器。

## 从层级数据创建列表

- **init(_:children:rowContent:)**：创建一个层级列表，该列表根据绑定到底层可识别数据集合的绑定按需计算其行。

- **init(_:children:selection:rowContent:)**：创建一个层级列表，该列表根据绑定到底层可识别数据集合的绑定按需计算其行，并允许用户始终选中且仅选中一行。

- **init(_:id:children:rowContent:)**：创建一个层级列表，该列表基于指向底层数据标识符的键路径来标识其行。


---
source: https://developer.apple.com/documentation/SwiftUI/List/init(_:id:children:selection:rowContent:)
crawled: 2025-12-01T10:31:53Z
---

# init(_:id:children:selection:rowContent:)

**Initializer**

Creates a hierarchical list that identifies its rows based on a key path to the identifier of the underlying data and allowing users to have exactly one row always selected.

## Declaration

```swift
@MainActor @preconcurrency init<Data, ID, RowContent>(_ data: Binding<Data>, id: KeyPath<Data.Element, ID>, children: WritableKeyPath<Data.Element, Data?>, selection: Binding<SelectionValue>, @ViewBuilder rowContent: @escaping (Binding<Data.Element>) -> RowContent) where Content == OutlineGroup<Binding<Data>, ID, RowContent, RowContent, DisclosureGroup<RowContent, OutlineSubgroupChildren>>, Data : MutableCollection, Data : RandomAccessCollection, ID : Hashable, RowContent : View
```

## Parameters

- **data**: The data for populating the list.
- **id**: The key path to the data model’s identifier.
- **children**: A key path to a property whose non-`nil` value gives the children of `data`. A non-`nil` but empty value denotes a node capable of having children that is currently childless, such as an empty directory in a file system. On the other hand, if the property at the key path is `nil`, then `data` is treated as a leaf node in the tree, like a regular file in a file system.
- **selection**: A binding to a non optional selected value.
- **rowContent**: A view builder that creates the view for a single row of the list.

## Creating a list from hierarchical data

- **init(_:children:rowContent:)**: Creates a hierarchical list that computes its rows on demand from a binding to an underlying collection of identifiable data.
- **init(_:children:selection:rowContent:)**: Creates a hierarchical list that computes its rows on demand from a binding to an underlying collection of identifiable data and allowing users to have exactly one row always selected.
- **init(_:id:children:rowContent:)**: Creates a hierarchical list that identifies its rows based on a key path to the identifier of the underlying data.

