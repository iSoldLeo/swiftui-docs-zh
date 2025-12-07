--- 来源：https://developer.apple.com/documentation/SwiftUI/View/itemProvider(_:)

抓取时间：2025-11-30T21:27:53Z

---

# itemProvider(_:)

**实例方法**

提供一个闭包，用于提供特定数据元素的拖放表示。

## 声明

```swift
nonisolated func itemProvider(_ action: Optional<() -> NSItemProvider?>) -> some View

```

## 使用项目提供程序移动项目

- **onDrag(_:preview:)**：激活此视图作为拖放操作的源。

- **onDrag(_:)**：激活此视图作为拖放操作的源。

- **onDrop(of:isTargeted:perform:)**：定义拖放操作的目标位置，该位置使用您指定的闭包处理拖放的内容。

- **onDrop(of:delegate:)**：定义拖放操作的目标位置，该目标位置的行为由您提供的委托控制。

- **DropDelegate**：您实现的接口，用于与已修改为接受拖放操作的视图中的拖放操作进行交互。

- **DropProposal**：拖放操作的行为。

- **DropOperation**：操作类型，用于确定用户拖放项目时拖放会话的解析方式。

- **DropInfo**：拖放操作的当前状态。


---
source: https://developer.apple.com/documentation/SwiftUI/View/itemProvider(_:)
crawled: 2025-11-30T21:27:53Z
---

# itemProvider(_:)

**Instance Method**

Provides a closure that vends the drag representation to be used for a particular data element.

## Declaration

```swift
nonisolated func itemProvider(_ action: Optional<() -> NSItemProvider?>) -> some View

```

## Moving items using item providers

- **onDrag(_:preview:)**: Activates this view as the source of a drag and drop operation.
- **onDrag(_:)**: Activates this view as the source of a drag and drop operation.
- **onDrop(of:isTargeted:perform:)**: Defines the destination of a drag-and-drop operation that handles the dropped content with a closure that you specify.
- **onDrop(of:delegate:)**: Defines the destination of a drag and drop operation using behavior controlled by the delegate that you provide.
- **DropDelegate**: An interface that you implement to interact with a drop operation in a view modified to accept drops.
- **DropProposal**: The behavior of a drop.
- **DropOperation**: Operation types that determine how a drag and drop session resolves when the user drops a drag item.
- **DropInfo**: The current state of a drop.

