--- 来源：https://developer.apple.com/documentation/SwiftUI/View/draggable(_:)

抓取时间：2025-11-30T21:27:51Z

---

# draggable(_:)

**实例方法**

激活此视图作为拖放操作的源。

## 声明

```swift
nonisolated func draggable<T>(_ payload: @autoclosure @escaping () -> T) -> some View where T : Transferable

```

## 参数

- **payload**：一个闭包，返回一个符合 [doc://com.apple.documentation/documentation/CoreTransferable/Transferable] 的实例或值，表示此视图中的可拖动数据。

## 返回值

一个视图，激活此视图作为拖放操作的源，从用户手势输入开始。

## 说明

应用 `draggable(_:)` 修饰符会将相应的拖放手势添加到此视图。当拖放操作开始时，会生成此视图的渲染图并将其用作预览图像。

要自定义默认预览，请应用类型为 [dragPreview](../ContentShapeKinds/dragPreview.zh-Hans.md) 的 [contentShape(_:_:eoFill:)](contentShape_____eoFill.zh-Hans.md)。例如，您可以更改预览的圆角半径或使用嵌套视图作为预览。

## 移动可转移项目

- **draggable(_:preview:)**：激活此视图作为拖放操作的源。

- **dropDestination(for:action:isTargeted:)**：定义拖放操作的目标，该目标使用您指定的闭包处理放置的内容。


---
source: https://developer.apple.com/documentation/SwiftUI/View/draggable(_:)
crawled: 2025-11-30T21:27:51Z
---

# draggable(_:)

**Instance Method**

Activates this view as the source of a drag and drop operation.

## Declaration

```swift
nonisolated func draggable<T>(_ payload: @autoclosure @escaping () -> T) -> some View where T : Transferable

```

## Parameters

- **payload**: A closure that returns a single instance or a value conforming to [doc://com.apple.documentation/documentation/CoreTransferable/Transferable] that represents the draggable data from this view.

## Return Value

A view that activates this view as the source of a drag and drop operation, beginning with user gesture input.

## Discussion

Applying the `draggable(_:)` modifier adds the appropriate gestures for drag and drop to this view. When a drag operation begins, a rendering of this view is generated and used as the preview image.

To customize the default preview, apply a [contentShape(_:_:eoFill:)](contentShape_____eoFill.zh-Hans.md) with a [dragPreview](../ContentShapeKinds/dragPreview.zh-Hans.md) kind. For example, you can change the preview’s corner radius or use a nested view as the preview.

## Moving transferable items

- **draggable(_:preview:)**: Activates this view as the source of a drag and drop operation.
- **dropDestination(for:action:isTargeted:)**: Defines the destination of a drag and drop operation that handles the dropped content with a closure that you specify.

