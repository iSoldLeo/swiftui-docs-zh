--- 来源：https://developer.apple.com/documentation/SwiftUI/View/onDrop(of:delegate:)-2vr9o

抓取时间：2025-12-03T05:35:51Z

---

# onDrop(of:delegate:)

**实例方法**

定义拖放操作的目标位置，该位置与当前视图大小和位置相同，其行为由给定的委托控制。

## 声明

```swift
nonisolated func onDrop(of supportedTypes: [String], delegate: any DropDelegate) -> some View

```

## 参数

- **supportedTypes**：描述此视图可通过拖放操作接收的内容类型的统一类型标识符。如果拖放操作不包含任何受支持的类型，则此目标位置不会激活，并且 `isTargeted` 不会更新。

- **delegate**：符合 `DropDelegate` 协议的类型。使用委托时，您可以全面控制拖放行为。

## 返回值

返回一个视图，该视图为指定类型的拖放操作提供放置目标。


---
source: https://developer.apple.com/documentation/SwiftUI/View/onDrop(of:delegate:)-2vr9o
crawled: 2025-12-03T05:35:51Z
---

# onDrop(of:delegate:)

**Instance Method**

Defines the destination for a drag and drop operation with the same size and position as this view, with behavior controlled by the given delegate.

## Declaration

```swift
nonisolated func onDrop(of supportedTypes: [String], delegate: any DropDelegate) -> some View

```

## Parameters

- **supportedTypes**: The uniform type identifiers that describe the types of content this view can accept through drag and drop. If the drag and drop operation doesn’t contain any of the supported types, then this drop destination doesn’t activate and `isTargeted` doesn’t update.
- **delegate**: A type that conforms to the `DropDelegate` protocol. You have comprehensive control over drop behavior when you use a delegate.

## Return Value

A view that provides a drop destination for a drag operation of the specified types.

