--- 来源：https://developer.apple.com/documentation/SwiftUI/View/onDrop(of:isTargeted:perform:)

抓取时间：2025-12-02T17:42:50Z

---

# onDrop(of:isTargeted:perform:)

**实例方法**

定义拖放操作的目标位置，该位置使用您指定的闭包处理拖放的内容。

## 声明

```swift
nonisolated func onDrop(of supportedContentTypes: [UTType], isTargeted: Binding<Bool>?, perform action: @escaping ([NSItemProvider]) -> Bool) -> some View

```

## 参数

- **supportedContentTypes**：描述此视图可通过拖放操作接收的内容类型的统一类型标识符。如果拖放操作不包含任何受支持的类型，则此目标位置不会激活，并且 `isTargeted` 不会更新。

- **isTargeted**：当拖放操作进入或离开放置目标区域时，此绑定会更新。当光标位于区域内时，此绑定的值为 `true`；当光标位于区域外时，此绑定的值为 `false`。

- **action**：此闭包接收拖放的内容并做出相应的响应。`action` 的参数包含已拖放的项目，其类型由 `supportedContentTypes` 指定。如果拖放操作成功，则返回 `true`；否则，返回 `false`。

## 返回值

一个视图，为指定类型的拖放操作提供放置目标。

## 说明

放置目标的大小和位置与此视图相同。

请确保在 `action` 闭包的作用域内开始加载 `NSItemProvider` 实例的内容。不要在其他 Actor 上异步加载。内容加载可能会稍后完成，但必须从此处开始。出于安全考虑，放置接收器只能在此闭包返回之前访问已放置的有效负载。

## 使用项目提供程序移动项目

- **itemProvider(_:)**：提供一个闭包，用于提供特定数据元素的拖放表示。

- **onDrag(_:preview:)**：激活此视图作为拖放操作的源。

- **onDrag(_:)**：激活此视图作为拖放操作的源。

- **onDrop(of:delegate:)**：使用您提供的委托控制的行为定义拖放操作的目标。

- **DropDelegate**：用于与已修改为接受拖放操作的视图中的拖放操作进行交互的接口。

- **DropProposal**：拖放操作的行为。

- **DropOperation**：决定用户拖放项目时拖放会话如何结束的操作类型。

- **DropInfo**：拖放操作的当前状态。


---
source: https://developer.apple.com/documentation/SwiftUI/View/onDrop(of:isTargeted:perform:)
crawled: 2025-12-02T17:42:50Z
---

# onDrop(of:isTargeted:perform:)

**Instance Method**

Defines the destination of a drag-and-drop operation that handles the dropped content with a closure that you specify.

## Declaration

```swift
nonisolated func onDrop(of supportedContentTypes: [UTType], isTargeted: Binding<Bool>?, perform action: @escaping ([NSItemProvider]) -> Bool) -> some View

```

## Parameters

- **supportedContentTypes**: The uniform type identifiers that describe the types of content this view can accept through drag and drop. If the drag-and-drop operation doesn’t contain any of the supported types, then this drop destination doesn’t activate and `isTargeted` doesn’t update.
- **isTargeted**: A binding that updates when a drag and drop operation enters or exits the drop target area. The binding’s value is `true` when the cursor is inside the area, and `false` when the cursor is outside.
- **action**: A closure that takes the dropped content and responds appropriately. The parameter to `action` contains the dropped items, with types specified by `supportedContentTypes`. Return `true` if the drop operation was successful; otherwise, return `false`.

## Return Value

A view that provides a drop destination for a drag operation of the specified types.

## Discussion

The drop destination is the same size and position as this view.

Make sure to start loading the contents of `NSItemProvider` instances within the scope of the `action` closure. Do not perform loading asynchronously on a different actor. Loading the contents may finish later, but it must start here. For security reasons, the drop receiver can access the dropped payload only before this closure returns.

## Moving items using item providers

- **itemProvider(_:)**: Provides a closure that vends the drag representation to be used for a particular data element.
- **onDrag(_:preview:)**: Activates this view as the source of a drag and drop operation.
- **onDrag(_:)**: Activates this view as the source of a drag and drop operation.
- **onDrop(of:delegate:)**: Defines the destination of a drag and drop operation using behavior controlled by the delegate that you provide.
- **DropDelegate**: An interface that you implement to interact with a drop operation in a view modified to accept drops.
- **DropProposal**: The behavior of a drop.
- **DropOperation**: Operation types that determine how a drag and drop session resolves when the user drops a drag item.
- **DropInfo**: The current state of a drop.

