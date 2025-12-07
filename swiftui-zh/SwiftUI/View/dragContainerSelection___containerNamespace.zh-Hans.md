--- 来源：https://developer.apple.com/documentation/SwiftUI/View/dragContainerSelection(_:containerNamespace:)

抓取时间：2025-12-02T17:23:37Z

---

# dragContainerSelection(_:containerNamespace:)

**实例方法**

为拖拽容器提供多项选择支持。

## 声明

```swift
nonisolated func dragContainerSelection<ItemID>(_ selection: @autoclosure @escaping () -> Array<ItemID>, containerNamespace: Namespace.ID? = nil) -> some View where ItemID : Hashable, ItemID : Sendable

```

## 参数

- **selection**：提供所选项目标识符的闭包。

- **containerNamespace**：拖拽容器的可选命名空间。

## 说明

拖拽容器会找到与其具有相同项目标识符类型和相同命名空间（如果已指定）的最近的封闭容器 `dragContainerSelection(_:containerNamespace:)`。拖拽容器使用提供的所选项目标识符来确定拖拽有效负载的内容。

如果拖动的视图与选定的标识符关联，则有效负载应包含所有选定项。如果拖动的视图未被选中，则有效负载不应包含整个选定项，而应仅包含拖动的项。使用 `dragContainerSelection(_:containerNamespace:)`，您可以对拖动有效负载中包含的项进行精细控制。

```swift
    struct FruitContainer: View {
         @State private var fruits: [Fruit]
         @State private var selection: [Fruit.ID]

         var body: some View {
             VStack {
                 ForEach(fruits) { fruit in
                     FruitView(fruit)
                         .draggable(containerItemID: fruit.id)
                  }
              }
             .dragContainer(for: Fruit.self) { ids in
                 fruits(with: ids)
             }
             .dragContainerSelection(selection)
         }

       func fruits(with ids: [Fruit.ID]) -> [Fruit] { ... }

       struct Fruit: Transferable, Identifiable {
           let id: String
           ...
       }

       struct FruitView: View {
           init(_ fruit: Fruit) { ... }
       }
   }
```


---
source: https://developer.apple.com/documentation/SwiftUI/View/dragContainerSelection(_:containerNamespace:)
crawled: 2025-12-02T17:23:37Z
---

# dragContainerSelection(_:containerNamespace:)

**Instance Method**

Provides multiple item selection support for drag containers.

## Declaration

```swift
nonisolated func dragContainerSelection<ItemID>(_ selection: @autoclosure @escaping () -> Array<ItemID>, containerNamespace: Namespace.ID? = nil) -> some View where ItemID : Hashable, ItemID : Sendable

```

## Parameters

- **selection**: A closure that provides identifiers of selected items.
- **containerNamespace**: An optional namespace of the drag container.

## Discussion

A drag container finds the nearest enclosing `dragContainerSelection(_:containerNamespace:)` with the same item identifier type and same namespace, if specified. Drag container uses the provided selected item identifiers to determine what the drag payload should be.

If the dragged view is associated with a selected identifier, the payload should contain all the selected items. If the dragged view is not selected, the payload should not contain the whole selection, just the dragged item. With `dragContainerSelection(_:containerNamespace:)`, you get fine-grained control over what items are included in the drag payload.

```swift
    struct FruitContainer: View {
         @State private var fruits: [Fruit]
         @State private var selection: [Fruit.ID]

         var body: some View {
             VStack {
                 ForEach(fruits) { fruit in
                     FruitView(fruit)
                         .draggable(containerItemID: fruit.id)
                  }
              }
             .dragContainer(for: Fruit.self) { ids in
                 fruits(with: ids)
             }
             .dragContainerSelection(selection)
         }

       func fruits(with ids: [Fruit.ID]) -> [Fruit] { ... }

       struct Fruit: Transferable, Identifiable {
           let id: String
           ...
       }

       struct FruitView: View {
           init(_ fruit: Fruit) { ... }
       }
   }
```

