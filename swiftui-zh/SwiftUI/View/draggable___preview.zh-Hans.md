--- 来源：https://developer.apple.com/documentation/SwiftUI/View/draggable(_:preview:)

抓取时间：2025-11-30T21:27:52Z

---

# draggable(_:preview:)

**实例方法**

激活此视图作为拖放操作的源。

## 声明

```swift
nonisolated func draggable<V, T>(_ payload: @autoclosure @escaping () -> T, @ViewBuilder preview: () -> V) -> some View where V : View, T : Transferable

```

## 参数

- **payload**：一个闭包，返回一个类实例或符合 `Transferable` 的值，表示此视图中的可拖动数据。

- **preview**：一个 [View](../View.zh-Hans.md)，用作拖动操作开始后拖动预览的源。预览位于源视图的正上方。

## 返回值

激活此视图作为拖放操作的源，操作从用户手势输入开始。

## 说明

应用 `draggable(_:preview:)` 修饰符会将相应的拖放手势添加到此视图。拖动操作开始时，会生成 `preview` 的渲染图并将其用作预览图像。

```swift
var title: String
var body: some View {
    Color.pink
        .frame(width: 400, height: 400)
        .draggable(title) {
             Text("Drop me")
         }
}
```

要自定义系统过渡到显示自定义 `preview` 时显示的升降预览，请应用类型为 [dragPreview](../ContentShapeKinds/dragPreview.zh-Hans.md) 的 [contentShape(_:_:eoFill:)](contentShape_____eoFill.zh-Hans.md)。例如，您可以更改预览的圆角半径或使用嵌套视图作为预览。

## 移动可转移项目

- **draggable(_:)**：激活此视图作为拖放操作的源。

- **dropDestination(for:action:isTargeted:)**：定义拖放操作的目标位置，该位置使用您指定的闭包处理拖放的内容。


---
source: https://developer.apple.com/documentation/SwiftUI/View/draggable(_:preview:)
crawled: 2025-11-30T21:27:52Z
---

# draggable(_:preview:)

**Instance Method**

Activates this view as the source of a drag and drop operation.

## Declaration

```swift
nonisolated func draggable<V, T>(_ payload: @autoclosure @escaping () -> T, @ViewBuilder preview: () -> V) -> some View where V : View, T : Transferable

```

## Parameters

- **payload**: A closure that returns a single class instance or a value conforming to `Transferable` that represents the draggable data from this view.
- **preview**: A [View](../View.zh-Hans.md) to use as the source for the dragging preview, once the drag operation has begun. The preview is centered over the source view.

## Return Value

A view that activates this view as the source of a drag and drop operation, beginning with user gesture input.

## Discussion

Applying the `draggable(_:preview:)` modifier adds the appropriate gestures for drag and drop to this view. When a drag operation begins, a rendering of `preview` is generated and used as the preview image.

```swift
var title: String
var body: some View {
    Color.pink
        .frame(width: 400, height: 400)
        .draggable(title) {
             Text("Drop me")
         }
}
```

To customize the lift preview, shown while the system transitions to show your custom `preview`, apply a [contentShape(_:_:eoFill:)](contentShape_____eoFill.zh-Hans.md) with a [dragPreview](../ContentShapeKinds/dragPreview.zh-Hans.md) kind. For example, you can change the preview’s corner radius or use a nested view as the preview.

## Moving transferable items

- **draggable(_:)**: Activates this view as the source of a drag and drop operation.
- **dropDestination(for:action:isTargeted:)**: Defines the destination of a drag and drop operation that handles the dropped content with a closure that you specify.

