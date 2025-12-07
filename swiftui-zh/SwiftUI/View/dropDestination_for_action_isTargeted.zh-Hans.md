--- 来源：https://developer.apple.com/documentation/SwiftUI/View/dropDestination(for:action:isTargeted:)

抓取时间：2025-12-02T17:42:48Z

---

# dropDestination(for:action:isTargeted:)

**实例方法**

定义拖放操作的目标位置，该位置使用您指定的闭包处理拖放的内容。

## 声明

```swift
nonisolated func dropDestination<T>(for payloadType: T.Type = T.self, action: @escaping ([T], CGPoint) -> Bool, isTargeted: @escaping (Bool) -> Void = { _ in }) -> some View where T : Transferable

```

## 参数

- **payloadType**：拖放模型的预期类型。

- **action**：接收拖放内容并做出相应响应的闭包。`action` 的第一个参数包含拖放的项目。第二个参数包含在此视图坐标空间中的拖放位置。如果拖放操作成功，则返回 `true`；否则，返回 `false`。

- **isTargeted**：当拖放操作进入或离开目标区域时调用的闭包。当光标位于区域内时，接收到的值为 `true`；当光标位于区域外时，接收到的值为 `false`。

## 返回值

为指定类型的拖放操作提供目标位置的视图。

## 说明

拖放的内容可以以二进制数据、文件 URL 或文件 Promise 的形式提供。

目标位置与此视图的大小和位置相同。

```swift
@State private var isDropTargeted = false

var body: some View {
    Color.pink
        .frame(width: 400, height: 400)
        .dropDestination(for: String.self) { receivedTitles, location in
            animateDrop(at: location)
            process(titles: receivedTitles)
        } isTargeted: {
            isDropTargeted = $0
        }
}

func process(titles: [String]) { ... }
func animateDrop(at: CGPoint) { ... }
```

## 移动可转移项

- **draggable(_:)**：激活此视图作为拖放操作的源。 - **draggable(_:preview:)**：启用此视图作为拖放操作的源视图。


---
source: https://developer.apple.com/documentation/SwiftUI/View/dropDestination(for:action:isTargeted:)
crawled: 2025-12-02T17:42:48Z
---

# dropDestination(for:action:isTargeted:)

**Instance Method**

Defines the destination of a drag and drop operation that handles the dropped content with a closure that you specify.

## Declaration

```swift
nonisolated func dropDestination<T>(for payloadType: T.Type = T.self, action: @escaping ([T], CGPoint) -> Bool, isTargeted: @escaping (Bool) -> Void = { _ in }) -> some View where T : Transferable

```

## Parameters

- **payloadType**: The expected type of the dropped models.
- **action**: A closure that takes the dropped content and responds appropriately. The first parameter to `action` contains the dropped items. The second parameter contains the drop location in this view’s coordinate space. Return `true` if the drop operation was successful; otherwise, return `false`.
- **isTargeted**: A closure that is called when a drag and drop operation enters or exits the drop target area. The received value is `true` when the cursor is inside the area, and `false` when the cursor is outside.

## Return Value

A view that provides a drop destination for a drag operation of the specified type.

## Discussion

The dropped content can be provided as binary data, file URLs, or file promises.

The drop destination is the same size and position as this view.

```swift
@State private var isDropTargeted = false

var body: some View {
    Color.pink
        .frame(width: 400, height: 400)
        .dropDestination(for: String.self) { receivedTitles, location in
            animateDrop(at: location)
            process(titles: receivedTitles)
        } isTargeted: {
            isDropTargeted = $0
        }
}

func process(titles: [String]) { ... }
func animateDrop(at: CGPoint) { ... }
```

## Moving transferable items

- **draggable(_:)**: Activates this view as the source of a drag and drop operation.
- **draggable(_:preview:)**: Activates this view as the source of a drag and drop operation.

