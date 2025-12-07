--- 来源：https://developer.apple.com/documentation/SwiftUI/List/init(_:id:editActions:rowContent:)

抓取时间：2025-12-03T05:42:48Z

---

# init(_:id:editActions:rowContent:)

**Initializer**

创建一个列表，该列表根据底层可识别数据集合按需计算行，并允许编辑该集合。

## 声明

```swift
@MainActor @preconcurrency init<Data, ID, RowContent>(_ data: Binding<Data>, id: KeyPath<Data.Element, ID>, editActions: EditActions<Data>, @ViewBuilder rowContent: @escaping (Binding<Data.Element>) -> RowContent) where Content == ForEach<IndexedIdentifierCollection<Data, ID>, ID, EditableCollectionContent<RowContent, Data>>, Data : MutableCollection, Data : RandomAccessCollection, ID : Hashable, RowContent : View, Data.Index : Hashable
```

## 参数

- **data**：用于计算列表的可识别数据集合。

- **id**：指向数据模型标识符的键路径。

- **editActions**：在 `data` 上合成的编辑操作。

- **rowContent**：用于创建列表中单行视图的视图构建器。

## 讨论

以下示例创建一个列表，用于显示用户收藏的食物集合，并允许用户删除或移动集合中的元素。

```swift
List($foods, editActions: [.delete, .move]) { $food in
   HStack {
       Text(food.name)
       Toggle("Favorite", isOn: $food.isFavorite)
   }
}
```

使用 [deleteDisabled(_:)](../View/deleteDisabled.zh-Hans.md) 和 [moveDisabled(_:)](../View/moveDisabled.zh-Hans.md) 分别禁用每行的删除或移动操作。

显式的 `DynamicViewContent.onDelete(perform:)`、`DynamicViewContent.onMove(perform:)` 或 `View.swipeActions(edge:allowsFullSwipe:content:)` 修饰符将覆盖任何合成操作。

## 从可编辑数据创建列表

- **init(_:editActions:rowContent:)**：创建一个列表，该列表根据底层可识别数据集合按需计算其行，并允许编辑该集合。

- **init(_:editActions:selection:rowContent:)**：创建一个列表，该列表根据底层可识别数据集合按需计算其行，允许编辑该集合，并且需要选择单行。

- **init(_:id:editActions:selection:rowContent:)**：创建一个列表，该列表根据底层可识别数据集合按需计算其行，允许编辑该集合，并且需要选择单行。


---
source: https://developer.apple.com/documentation/SwiftUI/List/init(_:id:editActions:rowContent:)
crawled: 2025-12-03T05:42:48Z
---

# init(_:id:editActions:rowContent:)

**Initializer**

Creates a list that computes its rows on demand from an underlying collection of identifiable data and enables editing the collection.

## Declaration

```swift
@MainActor @preconcurrency init<Data, ID, RowContent>(_ data: Binding<Data>, id: KeyPath<Data.Element, ID>, editActions: EditActions<Data>, @ViewBuilder rowContent: @escaping (Binding<Data.Element>) -> RowContent) where Content == ForEach<IndexedIdentifierCollection<Data, ID>, ID, EditableCollectionContent<RowContent, Data>>, Data : MutableCollection, Data : RandomAccessCollection, ID : Hashable, RowContent : View, Data.Index : Hashable
```

## Parameters

- **data**: A collection of identifiable data for computing the list.
- **id**: The key path to the data model’s identifier.
- **editActions**: The edit actions that are synthesized on `data`.
- **rowContent**: A view builder that creates the view for a single row of the list.

## Discussion

The following example creates a list to display a collection of favorite foods allowing the user to delete or move elements from the collection.

```swift
List($foods, editActions: [.delete, .move]) { $food in
   HStack {
       Text(food.name)
       Toggle("Favorite", isOn: $food.isFavorite)
   }
}
```

Use [deleteDisabled(_:)](../View/deleteDisabled.zh-Hans.md) and [moveDisabled(_:)](../View/moveDisabled.zh-Hans.md) to disable respectively delete or move actions on a per-row basis.

Explicit `DynamicViewContent.onDelete(perform:)`, `DynamicViewContent.onMove(perform:)`, or `View.swipeActions(edge:allowsFullSwipe:content:)` modifiers will override any synthesized action

## Creating a list from editable data

- **init(_:editActions:rowContent:)**: Creates a list that computes its rows on demand from an underlying collection of identifiable data and enables editing the collection.
- **init(_:editActions:selection:rowContent:)**: Creates a list that computes its rows on demand from an underlying collection of identifiable data, enables editing the collection, and requires a selection of a single row.
- **init(_:id:editActions:selection:rowContent:)**: Creates a list that computes its rows on demand from an underlying collection of identifiable data, enables editing the collection, and requires a selection of a single row.

