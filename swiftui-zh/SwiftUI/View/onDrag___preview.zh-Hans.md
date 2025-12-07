--- 来源：https://developer.apple.com/documentation/SwiftUI/View/onDrag(_:preview:)

抓取时间：2025-12-02T17:42:49Z

---

# onDrag(_:preview:)

**实例方法**

激活此视图作为拖放操作的源。

## 声明

```swift
nonisolated func onDrag<V>(_ data: @escaping () -> NSItemProvider, @ViewBuilder preview: () -> V) -> some View where V : View

```

## 参数

- **data**：一个闭包，返回一个 [doc://com.apple.documentation/documentation/Foundation/NSItemProvider]，表示此视图中的可拖动数据。

- **preview**：一个 [View](../View.zh-Hans.md)，用作拖动操作开始后的拖动预览源。预览位于源视图的正上方。

## 返回值

此视图激活后，即可作为拖放操作的源视图，操作从用户手势输入开始。

## 说明

应用 `onDrag(_:preview:)` 修饰符会将相应的拖放手势添加到此视图。拖动操作开始时，会生成 `preview` 的渲染图并将其用作预览图像。

要自定义系统过渡到显示自定义 `preview` 时显示的升降预览，请应用类型为 [dragPreview](../ContentShapeKinds/dragPreview.zh-Hans.md) 的 [contentShape(_:_:eoFill:)](contentShape_____eoFill.zh-Hans.md)。例如，您可以更改预览的圆角半径或使用嵌套视图作为预览。

## 使用项目提供程序移动项目

- **itemProvider(_:)**：提供一个闭包，用于提供特定数据元素的拖动表示形式。

- **onDrag(_:)**：激活此视图作为拖放操作的源。

- **onDrop(of:isTargeted:perform:)**：定义拖放操作的目标位置，该位置使用您指定的闭包处理放置的内容。

- **onDrop(of:delegate:)**：定义拖放操作的目标位置，该目标位置使用您提供的委托控制的行为。

- **DropDelegate**：您实现的接口，用于与已修改为接受放置操作的视图中的放置操作进行交互。

- **DropProposal**：放置操作的行为。

- **DropOperation**：操作类型，用于确定用户放置拖动项时拖放会话的解析方式。

- **DropInfo**：放置操作的当前状态。


---
source: https://developer.apple.com/documentation/SwiftUI/View/onDrag(_:preview:)
crawled: 2025-12-02T17:42:49Z
---

# onDrag(_:preview:)

**Instance Method**

Activates this view as the source of a drag and drop operation.

## Declaration

```swift
nonisolated func onDrag<V>(_ data: @escaping () -> NSItemProvider, @ViewBuilder preview: () -> V) -> some View where V : View

```

## Parameters

- **data**: A closure that returns a single [doc://com.apple.documentation/documentation/Foundation/NSItemProvider] that represents the draggable data from this view.
- **preview**: A [View](../View.zh-Hans.md) to use as the source for the dragging preview, once the drag operation has begun. The preview is centered over the source view.

## Return Value

A view that activates this view as the source of a drag-and- drop operation, beginning with user gesture input.

## Discussion

Applying the `onDrag(_:preview:)` modifier adds the appropriate gestures for drag and drop to this view. When a drag operation begins, a rendering of `preview` is generated and used as the preview image.

To customize the lift preview, shown while the system transitions to show your custom `preview`, apply a [contentShape(_:_:eoFill:)](contentShape_____eoFill.zh-Hans.md) with a [dragPreview](../ContentShapeKinds/dragPreview.zh-Hans.md) kind. For example, you can change the preview’s corner radius or use a nested view as the preview.

## Moving items using item providers

- **itemProvider(_:)**: Provides a closure that vends the drag representation to be used for a particular data element.
- **onDrag(_:)**: Activates this view as the source of a drag and drop operation.
- **onDrop(of:isTargeted:perform:)**: Defines the destination of a drag-and-drop operation that handles the dropped content with a closure that you specify.
- **onDrop(of:delegate:)**: Defines the destination of a drag and drop operation using behavior controlled by the delegate that you provide.
- **DropDelegate**: An interface that you implement to interact with a drop operation in a view modified to accept drops.
- **DropProposal**: The behavior of a drop.
- **DropOperation**: Operation types that determine how a drag and drop session resolves when the user drops a drag item.
- **DropInfo**: The current state of a drop.

