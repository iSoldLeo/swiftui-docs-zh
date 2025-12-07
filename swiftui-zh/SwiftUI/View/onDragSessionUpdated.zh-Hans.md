--- 来源：https://developer.apple.com/documentation/SwiftUI/View/onDragSessionUpdated(_:)

抓取时间：2025-11-30T21:10:01Z

---

# onDragSessionUpdated(_:)

**实例方法**

指定在每次由 `draggable(_:)` 或其他拖拽修饰符激活的拖拽操作更新时要执行的操作。

## 声明

```swift
nonisolated func onDragSessionUpdated(_ onUpdate: @escaping (DragSession) -> Void) -> some View

```

## 讨论

以下示例视图显示一本书，并支持拖拽复制、移动和删除操作。如果会话以移动或删除项目结束，则在 `onUpdate` 闭包中，视图会通知模型层应从源中删除该书。

```swift
   struct DraggableBookView: View {
       var id: UUID

       var body: some View {
           BookView()
               .draggable(
                   configuration: DragConfiguration(
                       operationsWithinApp: .init(allowMove: true, allowDelete: true),
                       operationsOutsideApp: .init(allowMove: true, allowDelete: true)
                   ), Book(id: id))
               .onDragSessionUpdated { session in
                   switch session.phase {
                   case .ended(at: _, with: let operation):
                       if operation == .move || operation == .delete {
                           if let id = session.draggedItemIDs(type: UUID.self).first {
                               removeBook(id: id)
                           }
                       }
                   default:
                       break
                   }
               }
       }
   }

   func removeBook(id: UUID) { }
```

当子视图层级结构中最近的拖拽会话变为活动状态时，将调用 `onUpdate` 闭包。


---
source: https://developer.apple.com/documentation/SwiftUI/View/onDragSessionUpdated(_:)
crawled: 2025-11-30T21:10:01Z
---

# onDragSessionUpdated(_:)

**Instance Method**

Specifies an action to perform on each update of an ongoing dragging operation activated by `draggable(_:)` or anther drag modifiers.

## Declaration

```swift
nonisolated func onDragSessionUpdated(_ onUpdate: @escaping (DragSession) -> Void) -> some View

```

## Discussion

Below is an example of a view that displays a book and supports dragging to copy, move, and delete. If the session ends with moving or deleting the item, in the `onUpdate` closure, the view lets the model layer know that the book should be deleted from the source.

```swift
   struct DraggableBookView: View {
       var id: UUID

       var body: some View {
           BookView()
               .draggable(
                   configuration: DragConfiguration(
                       operationsWithinApp: .init(allowMove: true, allowDelete: true),
                       operationsOutsideApp: .init(allowMove: true, allowDelete: true)
                   ), Book(id: id))
               .onDragSessionUpdated { session in
                   switch session.phase {
                   case .ended(at: _, with: let operation):
                       if operation == .move || operation == .delete {
                           if let id = session.draggedItemIDs(type: UUID.self).first {
                               removeBook(id: id)
                           }
                       }
                   default:
                       break
                   }
               }
       }
   }

   func removeBook(id: UUID) { }
```

The `onUpdate` closure is called when the closest drag session in the child view hierarchy becomes active.

