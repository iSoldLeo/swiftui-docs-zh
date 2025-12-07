--- 来源：https://developer.apple.com/documentation/SwiftUI/View/onDrag(_:)

抓取时间：2025-11-30T21:27:55Z

---

# onDrag(_:)

**实例方法**

激活此视图作为拖放操作的源。

## 声明

```swift
nonisolated func onDrag(_ data: @escaping () -> NSItemProvider) -> some View

```

## 参数

- **data**：一个闭包，返回一个 [doc://com.apple.documentation/documentation/Foundation/NSItemProvider]，表示此视图中的可拖动数据。

## 返回值

一个视图，该视图激活此视图作为拖放操作的源，从用户手势输入开始。

## 说明

应用 `onDrag(_:)` 修饰符会将相应的拖放手势添加到此视图。当拖放操作开始时，系统会生成此视图的渲染结果并将其用作预览图像。

要自定义默认预览，请应用类型为 [dragPreview](../ContentShapeKinds/dragPreview.zh-Hans.md) 的 [contentShape(_:_:eoFill:)](contentShape_____eoFill.zh-Hans.md)。例如，您可以更改预览的圆角半径或使用嵌套视图作为预览。

如果您想显示不同的预览，可以使用 [onDrag(_:preview:)](onDrag___preview.zh-Hans.md)。

## 使用项目提供程序移动项目

- **itemProvider(_:)**：提供一个闭包，用于提供特定数据元素的拖放表示形式。

- **onDrag(_:preview:)**：激活此视图作为拖放操作的源。

- **onDrop(of:isTargeted:perform:)**：定义拖放操作的目标，该目标使用您指定的闭包处理放置的内容。

- **onDrop(of:delegate:)**：定义拖放操作的目标位置，该目标位置的行为由您提供的委托控制。

- **DropDelegate**：您实现的接口，用于与已修改为接受拖放操作的视图中的拖放操作进行交互。

- **DropProposal**：拖放操作的行为。

- **DropOperation**：操作类型，用于确定用户拖放项目时拖放会话的解析方式。

- **DropInfo**：拖放操作的当前状态。


---
source: https://developer.apple.com/documentation/SwiftUI/View/onDrag(_:)
crawled: 2025-11-30T21:27:55Z
---

# onDrag(_:)

**Instance Method**

Activates this view as the source of a drag and drop operation.

## Declaration

```swift
nonisolated func onDrag(_ data: @escaping () -> NSItemProvider) -> some View

```

## Parameters

- **data**: A closure that returns a single [doc://com.apple.documentation/documentation/Foundation/NSItemProvider] that represents the draggable data from this view.

## Return Value

A view that activates this view as the source of a drag and drop operation, beginning with user gesture input.

## Discussion

Applying the `onDrag(_:)` modifier adds the appropriate gestures for drag and drop to this view. When a drag operation begins, a rendering of this view is generated and used as the preview image.

To customize the default preview, apply a [contentShape(_:_:eoFill:)](contentShape_____eoFill.zh-Hans.md) with a [dragPreview](../ContentShapeKinds/dragPreview.zh-Hans.md) kind. For example, you can change the preview’s corner radius or use a nested view as the preview.

If you want to show a different preview, you can use [onDrag(_:preview:)](onDrag___preview.zh-Hans.md).

## Moving items using item providers

- **itemProvider(_:)**: Provides a closure that vends the drag representation to be used for a particular data element.
- **onDrag(_:preview:)**: Activates this view as the source of a drag and drop operation.
- **onDrop(of:isTargeted:perform:)**: Defines the destination of a drag-and-drop operation that handles the dropped content with a closure that you specify.
- **onDrop(of:delegate:)**: Defines the destination of a drag and drop operation using behavior controlled by the delegate that you provide.
- **DropDelegate**: An interface that you implement to interact with a drop operation in a view modified to accept drops.
- **DropProposal**: The behavior of a drop.
- **DropOperation**: Operation types that determine how a drag and drop session resolves when the user drops a drag item.
- **DropInfo**: The current state of a drop.

