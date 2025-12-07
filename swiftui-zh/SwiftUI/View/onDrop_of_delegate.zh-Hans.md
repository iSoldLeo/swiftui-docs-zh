--- 来源：https://developer.apple.com/documentation/SwiftUI/View/onDrop(of:delegate:)

抓取时间：2025-11-30T21:27:56Z

---

# onDrop(of:delegate:)

**实例方法**

定义拖放操作的目标位置，该位置使用您提供的委托控制的行为。

## 声明

```swift
nonisolated func onDrop(of supportedContentTypes: [UTType], delegate: any DropDelegate) -> some View

```

## 参数

- **supportedContentTypes**：描述此视图可通过拖放操作接收的内容类型的统一类型标识符。如果拖放操作不包含任何受支持的类型，则此目标位置不会激活，并且 `isTargeted` 不会更新。

- **delegate**：符合 [DropDelegate](../DropDelegate.zh-Hans.md) 协议的类型。使用委托时，您可以全面控制拖放行为。

## 返回值

为指定类型的拖放操作提供放置目标的视图。

## 使用项目提供程序移动项目

- **itemProvider(_:)**：提供一个闭包，用于提供特定数据元素的拖放表示形式。

- **onDrag(_:preview:)**：激活此视图作为拖放操作的源。

- **onDrag(_:)**：激活此视图作为拖放操作的源。

- **onDrop(of:isTargeted:perform:)**：定义拖放操作的目标，该目标使用您指定的闭包处理放置的内容。

- **DropDelegate**：用于与已修改为接受拖放操作的视图中的拖放操作进行交互的接口。

- **DropProposal**：拖放操作的行为。

- **DropOperation**：决定用户拖放项目时拖放会话如何解析的操作类型。

- **DropInfo**：拖放操作的当前状态。


---
source: https://developer.apple.com/documentation/SwiftUI/View/onDrop(of:delegate:)
crawled: 2025-11-30T21:27:56Z
---

# onDrop(of:delegate:)

**Instance Method**

Defines the destination of a drag and drop operation using behavior controlled by the delegate that you provide.

## Declaration

```swift
nonisolated func onDrop(of supportedContentTypes: [UTType], delegate: any DropDelegate) -> some View

```

## Parameters

- **supportedContentTypes**: The uniform type identifiers that describe the types of content this view can accept through drag and drop. If the drag and drop operation doesn’t contain any of the supported types, then this drop destination doesn’t activate and `isTargeted` doesn’t update.
- **delegate**: A type that conforms to the [DropDelegate](../DropDelegate.zh-Hans.md) protocol. You have comprehensive control over drop behavior when you use a delegate.

## Return Value

A view that provides a drop destination for a drag operation of the specified types.

## Moving items using item providers

- **itemProvider(_:)**: Provides a closure that vends the drag representation to be used for a particular data element.
- **onDrag(_:preview:)**: Activates this view as the source of a drag and drop operation.
- **onDrag(_:)**: Activates this view as the source of a drag and drop operation.
- **onDrop(of:isTargeted:perform:)**: Defines the destination of a drag-and-drop operation that handles the dropped content with a closure that you specify.
- **DropDelegate**: An interface that you implement to interact with a drop operation in a view modified to accept drops.
- **DropProposal**: The behavior of a drop.
- **DropOperation**: Operation types that determine how a drag and drop session resolves when the user drops a drag item.
- **DropInfo**: The current state of a drop.

