---
来源：https://developer.apple.com/documentation/SwiftUI/OutlineGroup/init(_:children:content:)
抓取时间： 2025-12-01T09:06:11Z
---

# init(_:children:content:)

**Initializer**

根据根数据元素集合的绑定及其子元素的关键路径创建大纲组。

### 声明

```swift
init<C, E>(_ data: Binding<C>, children: WritableKeyPath<E, C?>, @ViewBuilder content: @escaping (Binding<E>) -> Leaf) where Data == Binding<C>, ID == E.ID, C : MutableCollection, C : RandomAccessCollection, E : Identifiable, E == C.Element
```

## 参数

- **data**：树形结构的标识数据集合。
- **children**：属性的关键路径，其非`nil` 值给出`data` 的子属性。非`nil`但为空的值表示一个可以有子元素但目前没有子元素，例如文件系统中的空目录。另一方面，如果关键路径上的属性是`nil`，那么大纲组就会把`data` 视为树中的叶子，就像文件系统中的普通文件一样。
- **content**：视图生成器，可根据`data` 中的元素生成内容视图。

### 讨论

该初始化程序创建了一个实例，可根据底层数据元素的标识在更新时唯一标识视图。

所有生成的披露组均以折叠状态开始。

请确保数据元素的标识符只有在要用新元素（具有新标识的元素）替换该元素时才会更改。如果元素的标识符发生变化，那么由该元素生成的内容视图将丢失任何当前状态和动画。

## 创建大纲组

- **init(_:children:)**：从根数据元素集合和元素子元素的关键路径创建一个大纲组。
- **init(_:id:children:content:)**：根据根数据元素集合的绑定、数据元素标识符的关键路径及其子元素的关键路径创建一个大纲组。


---
source: https://developer.apple.com/documentation/SwiftUI/OutlineGroup/init(_:children:content:)
crawled: 2025-12-01T09:06:11Z
---

# init(_:children:content:)

**Initializer**

Creates an outline group from a binding to a collection of root data elements and a key path to its children.

## Declaration

```swift
init<C, E>(_ data: Binding<C>, children: WritableKeyPath<E, C?>, @ViewBuilder content: @escaping (Binding<E>) -> Leaf) where Data == Binding<C>, ID == E.ID, C : MutableCollection, C : RandomAccessCollection, E : Identifiable, E == C.Element
```

## Parameters

- **data**: A collection of tree-structured, identified data.
- **children**: A key path to a property whose non-`nil` value gives the children of `data`. A non-`nil` but empty value denotes an element capable of having children that’s currently childless, such as an empty directory in a file system. On the other hand, if the property at the key path is `nil`, then the outline group treats `data` as a leaf in the tree, like a regular file in a file system.
- **content**: A view builder that produces a content view based on an element in `data`.

## Discussion

This initializer creates an instance that uniquely identifies views across updates based on the identity of the underlying data element.

All generated disclosure groups begin in the collapsed state.

Make sure that the identifier of a data element only changes if you mean to replace that element with a new element, one with a new identity. If the ID of an element changes, then the content view generated from that element will lose any current state and animations.

## Creating an outline group

- **init(_:children:)**: Creates an outline group from a collection of root data elements and a key path to element’s children.
- **init(_:id:children:content:)**: Creates an outline group from a binding to a collection of root data elements, the key path to a data element’s identifier, and a key path to its children.

