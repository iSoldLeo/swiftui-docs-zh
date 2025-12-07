---
来源： https://developer.apple.com/documentation/SwiftUI/IndexedIdentifierCollection
抓取时间： 2025-12-02T17:39:52Z
---

# IndexedIdentifierCollection

**Structure**

集合包装器，用于遍历集合的索引和标识符。

### 声明

```swift
struct IndexedIdentifierCollection<Base, ID> where Base : Collection, ID : Hashable
```

## 概览

您不会直接使用此类型。SwiftUI 会代表您创建此类型。

## 编辑列表

- **moveDisabled(_:)**：添加视图的视图层次结构是否可移动的条件。
- **deleteDisabled(_:)**：添加视图的视图层次结构是否可删除的条件。
- **editMode**：用户是否可以编辑与此环境关联的视图内容的指示。
- **EditMode**：表示用户是否可以编辑视图内容的模式。
- **EditActions**：视图可向用户提供的一组数据集合编辑操作。
- **EditableCollectionContent**：不透明封装视图，可为列表中的一行添加编辑功能。

## 符合

- 双向集合
- 集合
- 可复制
- 随机访问集合
- 序列


---
source: https://developer.apple.com/documentation/SwiftUI/IndexedIdentifierCollection
crawled: 2025-12-02T17:39:52Z
---

# IndexedIdentifierCollection

**Structure**

A collection wrapper that iterates over the indices and identifiers of a collection together.

## Declaration

```swift
struct IndexedIdentifierCollection<Base, ID> where Base : Collection, ID : Hashable
```

## Overview

You don’t use this type directly. Instead SwiftUI creates this type on your behalf.

## Editing a list

- **moveDisabled(_:)**: Adds a condition for whether the view’s view hierarchy is movable.
- **deleteDisabled(_:)**: Adds a condition for whether the view’s view hierarchy is deletable.
- **editMode**: An indication of whether the user can edit the contents of a view associated with this environment.
- **EditMode**: A mode that indicates whether the user can edit a view’s content.
- **EditActions**: A set of edit actions on a collection of data that a view can offer to a user.
- **EditableCollectionContent**: An opaque wrapper view that adds editing capabilities to a row in a list.

## Conforms To

- BidirectionalCollection
- Collection
- Copyable
- RandomAccessCollection
- Sequence

