--- 来源：https://developer.apple.com/documentation/SwiftUI/View/draggable(_:id:item:containerNamespace:)

抓取时间：2025-12-02T17:23:41Z

---

# draggable(_:id:item:containerNamespace:)

**实例方法**

激活此视图作为拖放操作的源，允许提供可选的有效负载并指定此视图所属的拖放容器的命名空间。

## 声明

```swift
nonisolated func draggable<Item, ItemID>(_ itemType: Item.Type = Item.self, id: KeyPath<Item, ItemID>, item: @autoclosure @escaping () -> Item?, containerNamespace: Namespace.ID? = nil) -> some View where Item : Transferable, ItemID : Hashable, ItemID : Sendable

```

## 参数

- **itemType**：被拖放项的类型。

- **id**：项的标识符。

- **containerNamespace**：关联的拖放容器的命名空间。

## 返回值

此视图会激活此视图，使其成为拖放操作的源，操作从用户手势输入开始。

## 说明

应用 `draggable(_:containerNamespace_:)` 修饰符会将相应的拖放手势添加到此视图。当拖放操作开始时，会生成此视图的渲染图并将其用作预览图像。

要自定义默认预览，请应用 [contentShape(_:_:eoFill:)](contentShape_____eoFill.zh-Hans.md) 修饰符，并指定类型为 [dragPreview](../ContentShapeKinds/dragPreview.zh-Hans.md)。例如，您可以更改预览的圆角半径或使用嵌套视图作为预览。


---
source: https://developer.apple.com/documentation/SwiftUI/View/draggable(_:id:item:containerNamespace:)
crawled: 2025-12-02T17:23:41Z
---

# draggable(_:id:item:containerNamespace:)

**Instance Method**

Activates this view as the source of a drag and drop operation, allowing to provide optional payload and specify the namespace of the drag container this view belongs to.

## Declaration

```swift
nonisolated func draggable<Item, ItemID>(_ itemType: Item.Type = Item.self, id: KeyPath<Item, ItemID>, item: @autoclosure @escaping () -> Item?, containerNamespace: Namespace.ID? = nil) -> some View where Item : Transferable, ItemID : Hashable, ItemID : Sendable

```

## Parameters

- **itemType**: A type of the dragged item.
- **id**: An identifier of an item.
- **containerNamespace**: A namespace of the associated drag container.

## Return Value

A view that activates this view as the source of a drag and drop operation, beginning with user gesture input.

## Discussion

Applying the `draggable(_:containerNamespace_:)` modifier adds the appropriate gestures for drag and drop to this view. When a drag operation begins, a rendering of this view is generated and used as the preview image.

To customize the default preview, apply a [contentShape(_:_:eoFill:)](contentShape_____eoFill.zh-Hans.md) with a [dragPreview](../ContentShapeKinds/dragPreview.zh-Hans.md) kind. For example, you can change the preview’s corner radius or use a nested view as the preview.

