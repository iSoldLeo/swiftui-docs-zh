--- 来源：https://developer.apple.com/documentation/SwiftUI/View/dragConfiguration(_:)

抓取时间：2025-12-02T17:23:34Z

---

# dragConfiguration(_:)

**实例方法**

配置拖拽会话。

## 声明

```swift
nonisolated func dragConfiguration(_ configuration: DragConfiguration) -> some View

```

## 参数

- **configuration**：描述拖拽会话配置的值。

## 返回值

一个视图，该视图以 `configuration` 参数描述的方式配置拖拽会话。

## 说明

以下是一个简化的视图示例，支持拖拽的复制、移动和删除操作。

### 拖拽删除到回收站

如果视图需要支持拖拽删除到回收站或其他类似语义位置的功能，则应在拖拽配置中指定对此操作的支持：

```swift
        @State private var photos: [Photo] = []
        @State private var selectedPhotos: [Photo.ID] = []

        var body: some View {
            ScrollView {
                LazyVGrid(columns: gridColumns) {
                    ForEach(photos) { photo in
                        PhotoView(photo: photo)
                            .draggable(containerItemID: photo.id)
                    }
                }
            }
            .dragContainer(for: Photo.self) { draggedIDs in
                photos(ids: draggedIDs)
            }
            .dragContainerSelection(selectedPhotos)
            .dragConfiguration(DragConfiguration(allowMove: false, allowDelete: true))
            .onDragSessionUpdated { session in
                if session.phase == .ended(.delete) {
                    let ids = session.draggedItemIDs(for: Photo.ID.self)
                    removeAndTrash(ids)
                }
            }
            .dragPreviewsFormation(.stack)
        }

        func removeAndTrash(_ ids: [Photo.ID]) {
            ids.forEach { id
                if let idx = photos.firstIndex(where: { $0.id == id }) {
                    let photo = photos[idx]
                    photos.remove(at: idx)
                    try? FileManager.default.trashItem(
                        at: photo.fileURL, resultingItemURL: nil
                    )
                }
            }
        }
    }
```

请注意，默认情况下，任何拖拽操作都支持复制操作。在上面的代码片段中，视图同时支持复制和删除操作。


---
source: https://developer.apple.com/documentation/SwiftUI/View/dragConfiguration(_:)
crawled: 2025-12-02T17:23:34Z
---

# dragConfiguration(_:)

**Instance Method**

Configures a drag session.

## Declaration

```swift
nonisolated func dragConfiguration(_ configuration: DragConfiguration) -> some View

```

## Parameters

- **configuration**: A value that describes the configuration of a drag session.

## Return Value

A view that configures a drag session in a way, described by the `configuration` parameter.

## Discussion

Below is a simplified example of a view that supports copy, move and delete operations for drag.

### Drag to delete into trash bin

If a view wants to support drag-to-delete into the trash bin or another location that has similar semantics, it should specify the support for this operation in a drag configuration:

```swift
        @State private var photos: [Photo] = []
        @State private var selectedPhotos: [Photo.ID] = []

        var body: some View {
            ScrollView {
                LazyVGrid(columns: gridColumns) {
                    ForEach(photos) { photo in
                        PhotoView(photo: photo)
                            .draggable(containerItemID: photo.id)
                    }
                }
            }
            .dragContainer(for: Photo.self) { draggedIDs in
                photos(ids: draggedIDs)
            }
            .dragContainerSelection(selectedPhotos)
            .dragConfiguration(DragConfiguration(allowMove: false, allowDelete: true))
            .onDragSessionUpdated { session in
                if session.phase == .ended(.delete) {
                    let ids = session.draggedItemIDs(for: Photo.ID.self)
                    removeAndTrash(ids)
                }
            }
            .dragPreviewsFormation(.stack)
        }

        func removeAndTrash(_ ids: [Photo.ID]) {
            ids.forEach { id
                if let idx = photos.firstIndex(where: { $0.id == id }) {
                    let photo = photos[idx]
                    photos.remove(at: idx)
                    try? FileManager.default.trashItem(
                        at: photo.fileURL, resultingItemURL: nil
                    )
                }
            }
        }
    }
```

Note, that any drag supports copy operation by default. In the snippet above, the view supports both copy and delete operations.

