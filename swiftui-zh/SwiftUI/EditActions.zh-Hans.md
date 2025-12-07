--- 来源：https://developer.apple.com/documentation/SwiftUI/EditActions
抓取时间：2025-12-02T17:39:51Z

---

# EditActions

**Structure**

一组视图可以向用户提供的、针对数据集合的编辑操作。

## 声明

```swift
struct EditActions<Data>
```

## 获取编辑操作

- **all**：此集合上所有可用的编辑操作。

- **all**：此集合上所有可用的编辑操作。

- **all**：此集合上所有可用的编辑操作。

- **all**：此集合上所有可用的编辑操作。

- **delete**：允许用户删除集合中一个或多个元素的编辑操作。

- **move**：允许用户移动集合中元素的编辑操作。

## 创建编辑操作

- **init(rawValue:)**：根据原始值创建新集合。

- **rawValue**：原始值。

## 编辑列表

- **moveDisabled(_:)**：添加一个条件，用于判断视图的视图层级结构是否可移动。

- **deleteDisabled(_:)**：添加一个条件，用于判断视图的视图层级结构是否可删除。

- **editMode**：指示用户是否可以编辑与此环境关联的视图的内容。

- **EditMode**：一种模式，用于指示用户是否可以编辑视图的内容。

- **EditableCollectionContent**：一个不透明的包装视图，用于为列表中的行添加编辑功能。

- **IndexedIdentifierCollection**：一个集合包装器，用于同时遍历集合的索引和标识符。

## 符合以下协议

- Equatable

- ExpressibleByArrayLiteral

- OptionSet

- RawRepresentable

- Sendable

- SendableMetatype

- SetAlgebra


---
source: https://developer.apple.com/documentation/SwiftUI/EditActions
crawled: 2025-12-02T17:39:51Z
---

# EditActions

**Structure**

A set of edit actions on a collection of data that a view can offer to a user.

## Declaration

```swift
struct EditActions<Data>
```

## Getting edit operations

- **all**: All the edit actions available on this collection.
- **all**: All the edit actions available on this collection.
- **all**: All the edit actions available on this collection.
- **all**: All the edit actions available on this collection.
- **delete**: An edit action that allows the user to delete one or more elements of a collection.
- **move**: An edit action that allows the user to move elements of a collection.

## Creating an edit operation

- **init(rawValue:)**: Creates a new set from a raw value.
- **rawValue**: The raw value.

## Editing a list

- **moveDisabled(_:)**: Adds a condition for whether the view’s view hierarchy is movable.
- **deleteDisabled(_:)**: Adds a condition for whether the view’s view hierarchy is deletable.
- **editMode**: An indication of whether the user can edit the contents of a view associated with this environment.
- **EditMode**: A mode that indicates whether the user can edit a view’s content.
- **EditableCollectionContent**: An opaque wrapper view that adds editing capabilities to a row in a list.
- **IndexedIdentifierCollection**: A collection wrapper that iterates over the indices and identifiers of a collection together.

## Conforms To

- Equatable
- ExpressibleByArrayLiteral
- OptionSet
- RawRepresentable
- Sendable
- SendableMetatype
- SetAlgebra

