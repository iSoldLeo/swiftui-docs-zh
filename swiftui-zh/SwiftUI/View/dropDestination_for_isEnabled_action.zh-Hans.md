--- 来源：https://developer.apple.com/documentation/SwiftUI/View/dropDestination(for:isEnabled:action:)

抓取时间：2025-11-30T21:08:47Z

---

# dropDestination(for:isEnabled:action:)

**实例方法**

定义拖放操作的目标位置，该操作提供拖放操作建议，并使用您指定的闭包处理拖放的内容。

## 声明

```swift
nonisolated func dropDestination<T>(for type: T.Type = T.self, isEnabled: Bool = true, action: @escaping ([T], DropSession) -> Void) -> some View where T : Transferable

```

## 参数

- **type**：预期的拖放模型类型。

- **isEnabled**：布尔值，指示视图是否接受拖放交互。

- **action**：接收拖放内容并做出相应响应的闭包。 `action` 的第一个参数包含已删除的项目。第二个参数包含删除会话描述。

## 返回值

返回一个视图，该视图为指定类型的删除操作提供目标位置。

## 说明

已删除的内容可以以二进制数据、文件 URL 或文件 Promise 的形式提供。

目标位置与此视图的大小和位置相同。

```swift
@State private var isDropTargeted = false
@Binding var isDropEnabled: Bool

var body: some View {
    Color.pink
        .frame(width: 400, height: 400)
        .dropDestination(
            for: String.self, isEnabled: isDropEnabled
        ) { receivedTitles, session in
            animateDrop(at: session.location)
            process(titles: receivedTitles)
        }
}

func process(titles: [String]) { ... }
func animateDrop(at: CGPoint) { ... }
```


---
source: https://developer.apple.com/documentation/SwiftUI/View/dropDestination(for:isEnabled:action:)
crawled: 2025-11-30T21:08:47Z
---

# dropDestination(for:isEnabled:action:)

**Instance Method**

Defines the destination of a drag and drop operation that provides a drop operation proposal and handles the dropped content with a closure that you specify.

## Declaration

```swift
nonisolated func dropDestination<T>(for type: T.Type = T.self, isEnabled: Bool = true, action: @escaping ([T], DropSession) -> Void) -> some View where T : Transferable

```

## Parameters

- **type**: The expected type of the dropped models.
- **isEnabled**: The Boolean value indicating if the view accepts drop interactions.
- **action**: A closure that takes the dropped content and responds appropriately. The first parameter to `action` contains the dropped items. The second parameter contains the drop session description.

## Return Value

A view that provides a drop destination for a drop operation of the specified type.

## Discussion

The dropped content can be provided as binary data, file URLs, or file promises.

The drop destination is the same size and position as this view.

```swift
@State private var isDropTargeted = false
@Binding var isDropEnabled: Bool

var body: some View {
    Color.pink
        .frame(width: 400, height: 400)
        .dropDestination(
            for: String.self, isEnabled: isDropEnabled
        ) { receivedTitles, session in
            animateDrop(at: session.location)
            process(titles: receivedTitles)
        }
}

func process(titles: [String]) { ... }
func animateDrop(at: CGPoint) { ... }
```

