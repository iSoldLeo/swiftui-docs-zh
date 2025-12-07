---
来源： https://developer.apple.com/documentation/SwiftUI/OutlineGroup/init(_:children:)
抓取时间： 2025-12-01T09:06:10Z
---

# init(_:children:)

**Initializer**

从根数据元素集合和元素子元素的关键路径创建大纲组。

### 声明

```swift
init<DataElement>(_ data: Data, children: KeyPath<DataElement, Data?>) where ID == DataElement.ID, Parent == TableRow<DataElement>, Leaf == TableRow<DataElement>, Subgroup == TableRow<DataElement>, DataElement : Identifiable, DataElement == Data.Element
```

## 参数

- **data**：树形结构的标识数据集合。
- **children**：属性的关键路径，其非`nil` 值给出`data` 的子属性。非`nil`但为空的值表示一个可以有子元素但目前没有子元素，例如文件系统中的空目录。另一方面，如果关键路径上的属性是`nil`，那么大纲组就会把`data` 视为树中的叶子，就像文件系统中的普通文件一样。

## 讨论

该初始化程序使用`TableRow` 为每个数据元素提供默认的`TableRowBuilder`。

该初始化程序会创建一个实例，根据底层数据元素的标识，在更新时唯一标识表行。

所有生成的披露组均以折叠状态开始。

## 创建大纲组

- **init(_:children:content:)**：根据根数据元素集合的绑定及其子元素的关键路径创建大纲组。
- **init(_:id:children:content:)**：根据根数据元素集合的绑定、数据元素标识符的关键路径及其子元素的关键路径创建一个大纲组。


---
source: https://developer.apple.com/documentation/SwiftUI/OutlineGroup/init(_:children:)
crawled: 2025-12-01T09:06:10Z
---

# init(_:children:)

**Initializer**

Creates an outline group from a collection of root data elements and a key path to element’s children.

## Declaration

```swift
init<DataElement>(_ data: Data, children: KeyPath<DataElement, Data?>) where ID == DataElement.ID, Parent == TableRow<DataElement>, Leaf == TableRow<DataElement>, Subgroup == TableRow<DataElement>, DataElement : Identifiable, DataElement == Data.Element
```

## Parameters

- **data**: A collection of tree-structured, identified data.
- **children**: A key path to a property whose non-`nil` value gives the children of `data`. A non-`nil` but empty value denotes an element capable of having children that’s currently childless, such as an empty directory in a file system. On the other hand, if the property at the key path is `nil`, then the outline group treats `data` as a leaf in the tree, like a regular file in a file system.

## Discussion

This initializer provides a default `TableRowBuilder` using `TableRow` for each data element.

This initializer creates an instance that uniquely identifies table rows across updates based on the identity of the underlying data element.

All generated disclosure groups begin in the collapsed state.

## Creating an outline group

- **init(_:children:content:)**: Creates an outline group from a binding to a collection of root data elements and a key path to its children.
- **init(_:id:children:content:)**: Creates an outline group from a binding to a collection of root data elements, the key path to a data element’s identifier, and a key path to its children.

