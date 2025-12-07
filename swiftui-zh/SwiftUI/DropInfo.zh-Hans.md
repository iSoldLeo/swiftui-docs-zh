--- 来源：https://developer.apple.com/documentation/SwiftUI/DropInfo
抓取时间：2025-12-02T17:42:54Z

---

# DropInfo

**Structure**

拖放的当前状态。

## 声明

```swift
struct DropInfo
```

## 获取拖放位置

- **location**：拖拽在拖放视图坐标空间中的位置。

## 检查项目

- **hasItemsConforming(to:)**：指示是否至少有一个项目符合至少一个指定的统一类型标识符。

- **itemProviders(for:)**：查找符合至少一个指定统一类型标识符的项目提供程序。

## 已弃用符号

- **hasItemsConforming(to:)**：返回是否存在至少一个符合指定统一类型标识符的项。

- **itemProviders(for:)**：返回一个数组，其中每个项都符合指定统一类型标识符的项。

## 实例方法

- **hasItemsConforming(to:)**：指示是否存在至少一个符合指定统一类型标识符的项。

- **itemProviders(for:)**：查找符合指定统一类型标识符的项提供程序。

## 使用项提供程序移动项

- **itemProvider(_:)**：提供一个闭包，用于提供特定数据元素的拖放表示形式。

- **onDrag(_:preview:)**：激活此视图作为拖放操作的源。

- **onDrag(_:)**：激活此视图作为拖放操作的源。

- **onDrop(of:isTargeted:perform:)**：定义拖放操作的目标位置，该位置使用您指定的闭包处理拖放的内容。

- **onDrop(of:delegate:)**：定义拖放操作的目标位置，该位置使用您提供的委托控制的行为。

- **DropDelegate**：您实现的接口，用于与已修改为接受拖放操作的视图中的拖放操作进行交互。

- **DropProposal**：拖放操作的行为。

- **DropOperation**：操作类型，用于确定用户拖放项目时拖放会话的解析方式。


---
source: https://developer.apple.com/documentation/SwiftUI/DropInfo
crawled: 2025-12-02T17:42:54Z
---

# DropInfo

**Structure**

The current state of a drop.

## Declaration

```swift
struct DropInfo
```

## Getting the drop location

- **location**: The location of the drag in the coordinate space of the drop view.

## Checking for items

- **hasItemsConforming(to:)**: Indicates whether at least one item conforms to at least one of the specified uniform type identifiers.
- **itemProviders(for:)**: Finds item providers that conform to at least one of the specified uniform type identifiers.

## Deprecated symbols

- **hasItemsConforming(to:)**: Returns whether at least one item conforms to at least one of the specified uniform type identifiers.
- **itemProviders(for:)**: Returns an array of items that each conform to at least one of the specified uniform type identifiers.

## Instance Methods

- **hasItemsConforming(to:)**: Indicates whether at least one item conforms to at least one of the specified uniform type identifiers.
- **itemProviders(for:)**: Finds item providers that conform to at least one of the specified uniform type identifiers.

## Moving items using item providers

- **itemProvider(_:)**: Provides a closure that vends the drag representation to be used for a particular data element.
- **onDrag(_:preview:)**: Activates this view as the source of a drag and drop operation.
- **onDrag(_:)**: Activates this view as the source of a drag and drop operation.
- **onDrop(of:isTargeted:perform:)**: Defines the destination of a drag-and-drop operation that handles the dropped content with a closure that you specify.
- **onDrop(of:delegate:)**: Defines the destination of a drag and drop operation using behavior controlled by the delegate that you provide.
- **DropDelegate**: An interface that you implement to interact with a drop operation in a view modified to accept drops.
- **DropProposal**: The behavior of a drop.
- **DropOperation**: Operation types that determine how a drag and drop session resolves when the user drops a drag item.

